## SafeAreaView in React Native

### Introduction ->

SafeAreaView is a built in component provided by react native ,which helps to render content within safe boundaries of device.

### How it works?

SafeAreaView only gives padding to our component so that it can be rendered effectively.

Note-> So if one is applying padding property to the SafeAreaView component it will have no effect.

### Pros->

-Most useful for iphone's having notches , as the content becomes messed up in the screen.


### Cons->
- It doesn't support android devices.



** So, then how can we effectively render content in safe area in android devices ?**
 -  We can use alternative method to implement same functionality,  by providing 
   paddingTop to the component.

### Solution->

- Use platform to identify the type of device - android or ios.
- If android then apply padding and if ios just give it any value .
- Code is implemented below

```
import React from "react";
import { Text,SafeAreaView,Platform,StyleSheet } from "react-native";



function App() {
  return (
    <SafeAreaView style={styles.app}>
      <Text>This is safearea component</Text>
      </SafeAreaView>
  )
}

const styles = StyleSheet.create({
  app: {
    marginHorizontal: "auto",
    paddingTop:Platform.OS==="android"?20:0,
    maxWidth: 500
  }
  
});

export default App;

``` 

Thanks for checking out. Stay tuned for more native content.
For more articles about development subscribe to the newsletter !



