## Flex position in native vs web



All of you have heard about flex property , it is a css positioning property.
To align items in flex mode we use justify-content and align-items property.
But the result of both will be different on mobile(native apps) vs desktop(web apps), if your are using react native stylesheet for mobile apps and css for web app.


**Let's understand the use of both the property
**

*justify-content:* to align item in primary axis

*align-items:* to align item in secondary axis


As the primary and secondary axis on both react-native(stylesheet) and web(css) are different .


![axis.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658727489728/MawhqUQhjR.png align="left")


Therefore you should apply this property keeping in mind about the axis.

