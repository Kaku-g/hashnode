## Creating Image Carousel in React Native

You will learn to implement  these-

  - React useState,useEffect hook
  - React native FlatList component
  - Api fetching and rendering


**The useState hook ->
**

```
// we are destructuring values to get images
// setImages is used to modify the content of images
// in the useState hook we are passing the initial values of the first parameter
//which is images and the value is empty array

const [images,setImages] = useState([])

``` 

**Api fetching
** 
We will be using pexel api for images. The api is free to use , all you need is to generate an API Key.

**How to generate API Key?
**
- SignUp on pexel is you don't have an account.
- Go to api section then fill out some basic details and then submit.
- Generate API Key 

**Using API
**


```

const API_KEY = " your key here";
const API_URL = "https://api.pexels.com/v1/search?query=nature&orientation=portrait&size=small&per_page=20";

//getting images using async function

const getImages = async () => {
    const data = await fetch(API_URL, {
      headers: {
        Authorization: API_KEY,
      },
    });

  // after getting the data we will get a lot of content
 // but we are destrcuturing it to get the data for photos

    const { photos } = await data.json();
    return photos;
  };



``` 

-  Next we will be using UseEffect hook to call the function (getImages) to save photo url 
   to our image.

```
 useEffect(() => {

//fetchImages for calling getImages function
// and setting images
// always use async await as the api take some time to return data

    const fetchImages = async () => {
      const imageList = await getImages();
      setImages(imageList);
    };
    fetchImages();
  }, []);

```

**What is FlatList component ?
**

It is a list item used to display your data. You pass a data object to it and it provides a renderItem method to render each data in object.
Its like using array.foreach in javascript. method .


Syntax for Flatlist


```
 <FlatList
// data property is for our object
// then it renders each item in the object

//by default the list is shown in vertical
//but we are using horizontal={true} to display in horizontal form(carousel)
//key extractor is a unique key valuein string  just like we used to give in react div 
  

       data={images}
        keyExtractor={(image) => image.id.toString()}
        horizontal
        pagingEnabled
        showsHorizontalScrollIndicator={false}
        renderItem={({ item }) => {

// applying styles to each item of object
//you are rendering a view to display each item (which is image in this case)
//to be shown in full screen

// width is width of your phone
//height is height of your phone
//width and height are coming from Dimensions method in native.

          return (
            <View>
              <Image

                style={{ width: width, height: height }}
                source={{ uri: item.src.portrait }}
              />

            </View>
          );
        }}
      />
``` 



 






**
Putting It All Together -> Implementing in React Native
**


```
import {FlatList, Image,View,Dimensions,SafeAreaView,StatusBar,StyleSheet} from "react-native";
import {useState,useEffect} from "react";
const { width, height } = Dimensions.get("screen");

const API_URL=  "https://api.pexels.com/v1/search?query=nature&orientation=portrait&size=small&per_page=20";

const API_KEY="your key here";

function WallpaperScreen(props) {
  const [images, setImages] = useState([]);

  const getImages = async () => {
    const data = await fetch(API_URL, {
      headers: {
        Authorization: API_KEY,
      },
    });

    const { photos } = await data.json();
    return photos;
  };

  useEffect(() => {
    const fetchImages = async () => {
      const imageList = await getImages();
      setImages(imageList);
    };
    fetchImages();
  }, []);

 return (
    <SafeAreaView style={styles.container}>
      <StatusBar hidden />
      <FlatList
       data={images}
        keyExtractor={(image) => image.id.toString()}
        horizontal
        pagingEnabled
        showsHorizontalScrollIndicator={false}
        renderItem={({ item }) => {
          return (
            <View>
              <Image
                style={{ width: width, height: height }}
                source={{ uri: item.src.portrait }}
                
              />
            </View>
          );
        }}
      />
    </SafeAreaView>
);
}

const styles= StyleSheet.create({
  container:{
    flex:1
  }
})

export default WallpaperScreen;
``` 

- The above will result in a simple carousel.You can change the url to get more images,
-  Read the pexel documentation for more info.




