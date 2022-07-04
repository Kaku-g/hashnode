## Creating Image Zoomin Zoomout effect with Fabric.js.....

Recently I came across a javascript framework  Fabric.js , used for creating canvas elements with simplicity and advance features.
In this tutorial we see how to use it to create a zoom effect using any custom image user upload.

Step-1
Create a index.html file .



Step-2
- Make sure to include the javascript file(fabric.js) and (home.js) in your root folder.
- Fabric.js file contains the code for interacting with the canvas element is provided by the dvelopers.
- Home.js files contains your js code for performing user actions on the canvas such as uploading any image and then performing zoom effect.
- The fabric.js file can be downloaded from this link ->



Your root folder should look like this

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655874299016/7NWCIxcIY.png align="left")


Step-3
Add some custom CSS for aligning the html elements.

Step-4 
Write you custom javascript file (home.js)


Codes for all the files

#index.html

```

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fabric.js project</title>
    <link rel="stylesheet" href="./home.css">
    <link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,700&display=swap"
/>
<link href="https://unpkg.com/material-components-web@latest/dist/material-components-web.min.css" rel="stylesheet">


</head>
<body>
    <div class="wrapper">
    <canvas id="c"></canvas>
    <label class="file">
        <input type="file" id="inp" aria-label="File browser example">
        <span class="file-custom"></span>
      </label>
    
   
</div>
    <script src="./fabric.js"></script>
    <script  src="./home.js"></script>
</body>
</html>

``` 

#css file

```#c{
    width:100%;
    height:70%;
   
}


.c{
    min-width: 800 !important;
    min-height: 500 !important;
    display: flex;
    align-items: center;
    align-content: center;
 
   

}

.wrapper{
    display: flex;
    flex-direction: column;
    align-content: center;
    align-self: center;
    align-items: center;
    border: 2px solid gray;
    margin-left:150px;
    margin-right: 150px;
    margin-top: 100px;
    padding-top: 10px;
    padding-bottom: 10px;
  
}

.uppercanvas{
    border: 2px solid gray;
    margin-left: 80px;
    margin-top: 80px;
}


input >#file-upload-button{
    border: 1px solid black;
    outline: none;
    padding: 5px;
}


``` 





#home.js

```



var canvas = new fabric.Canvas('c',{containerClass: 'c'}); // create a new fabric canvas

//setting height ,width and initial zoom of canvas 

canvas.setHeight(500);
canvas.setWidth(800);
canvas.setZoom(1.2);

//adding image upload functionality 
   document.getElementById("inp").addEventListener("change", function(e) {
      var file = e.target.files[0];
      var reader = new FileReader();
      reader.onload = function(f) {
         var data = f.target.result;
         fabric.Image.fromURL(data, function(img) {

            // adding our uploaded image as canvas background image
            
            canvas.setBackgroundImage(img, canvas.renderAll.bind(canvas), {
               scaleX: canvas.width / img.width,
               scaleY: canvas.height / img.height,
               left:20,
               right:20,
               
              
               
            });
         });
  
//for performing zoom in and zoom out effect

         canvas.on('mouse:wheel', function(opt) {
           var delta = opt.e.deltaY;
           var zoom = canvas.getZoom();
           zoom *= 0.999 ** delta;
           if (zoom > 20) zoom = 20;

// if zoom value goes below or equal to 1.2 it sets it back to 1.2
// this is done to prevent zooming out below the original image size

           if (zoom <=1.2) zoom = 1.2;
           canvas.zoomToPoint({ x: opt.e.offsetX, y: opt.e.offsetY }, zoom);
           
           opt.e.preventDefault();
           opt.e.stopPropagation();
      
        });
      
      
      };
      reader.readAsDataURL(file);
   });

``` 


