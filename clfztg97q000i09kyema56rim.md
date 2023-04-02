---
title: "Implement  Progress Bar  using React Hooks!"
datePublished: Sun Apr 02 2023 19:49:24 GMT+0000 (Coordinated Universal Time)
cuid: clfztg97q000i09kyema56rim
slug: implement-progress-bar-using-react-hooks
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xkBaqlcqeb4/upload/1e05dd071fb8ae0b1c0a09ff845ff1db.jpeg
tags: image-processing, programming-blogs, javascript, ux, reactjs

---

One of the most common problems while using images of large size is, rendering takes time and you don't wish to view empty image tags to users instead you can use a loading bar. It looks clean and professional.

In this post, we will be implementing a loading bar using React hooks.

Let us suppose we are fetching image urls from an API. After fetching the URL we want to display the image. We can use the following code.

```javascript


const Home=()=>{

const[data,setData]=useState([]);

/*
fetch your data from api here
api call and put it in -> data 

*/
const [loading,setLoading]=useState(true);
const [index,setIndex]=useState(0);

useEffect(()=>{
  
setLoading(true);
},[index])

const handleLoading =()=>{
setLoading(false);
}

const handlePrev=()=>{

if(index>=1)
 setIndex(index-1);
else
setIndex(data.length-1);

}

const handleNext=()=>{

if(index<data.length)
setIndex(index+1);
else
setIndex(0);
}


return(

{loading &&
<h1>Loading.....</h1>
}
{
!loading && 
<img src=data[index] onLoad={handleLoading} />
}

<button onClick={handlePrev}>Prev</button>
<button onClick={handleNext}>Next</button>
);
}
```

The above example demonstrates fetching images and showing them, also the prev and next buttons are used to change the index of the array(data) to render different images each time.

The onLoad function is called when the image is finished loading and therefore the loading state will be set to false and the image will be rendered on the web page. If the loading state is true the heading tag will show instead of the image and therefore the viewer will know that the image is loading, instead of showing the blank page.

Implementing a progress bar becomes very important for site performance as the viewer should be aware that some content is loading. It improves the overall experience of a user.

Thanks for reading!

Happy coding ;

PS: Check out the latest extension I released this week \[Tabster- Saving your tabs!\] to manage your chrome tabs.

[Get the extension](https://chrome.google.com/webstore/detail/tabster/epjkekcpjdffopichkinfjabbakeamhe?hl=en&authuser=0)