### **How to add a personalized skin**

#### -> Step by step guide

### 1) Add colors that you will want to use to variables.less (/AdminLTE/build/less/)
 -> I added these 2: @Iskratel: #429ADC;
		    @zeleniGumb: #37cc56;

### 2) When you have the selected colors added, then you can use them in your skin. So firstly make a copy of an already existing skin. I recommend that you decide here, if he is going to have light or dark sidebar.

### Now should your location have at least 1 copy of a skin here: /AdminLTE/build/less/skins
I had skin-blue-light.less and skin-blue-light(1).less. Rename the copy to the name that you want. 
I renamed it to skin-Iskratel.



### 3) Now you should edit the selected less file with the colors of your desire where needed.




### 4) Now your skin should be all done. Now import it in the file _all-skins.less (/AdminLTE/build/less/skins)
I added this line: @import "skin-Iskratel.less";

### 5) Time to compile all the files you added/changed to css.

I first instaled less globaly, so I wont have any problems ("npm install less -g")
Then you just compile using this formula:
"lessc FileYouWantToCompile.less FileYouWantToCompile.css"

##### IMPORTANT NOTE: Some compiled less files (css files) will need to be minified. I would advise you, to minify all at the start, so you dont have to look later on where the imported file is minified or not.

#### 6) After you did all this, there should be a skin made, there is just no way of selecting it. This function  will be added in a JavaScript files.
First add the colors, like you did in step 1, but this time in this file: app.js (/AdminLTE/dist/js).

Then add the skin you made to an array in demo.js (/AdminLTE/dist/js)
After that, you will have to copy some code.
Starting at currently 242 line, there is a script to add every skin separately. Depending, if you have
light or a dark skin, copy one of the already existing skins in that category. 

#####I copied this whole section: 

```
  var $skinBlueLight =
        $('<li />', { style: 'float:left; width: 33.33333%; padding: 5px;' })
          .append('<a href="javascript:void(0)" data-skin="skin-blue-light" style="display: block; box-shadow: 0 0 3px rgba(0,0,0,0.4)" class="clearfix full-opacity-hover">'
            + '<div><span style="display:block; width: 20%; float: left; height: 7px; background: #367fa9"></span><span class="bg-light-blue" style="display:block; width: 80%; float: left; height: 7px;"></span></div>'
            + '<div><span style="display:block; width: 20%; float: left; height: 20px; background: #f9fafc"></span><span style="display:block; width: 80%; float: left; height: 20px; background: #f4f5f7"></span></div>'
            + '</a>'
            + '<p class="text-center no-margin" style="font-size: 12px">Blue Light</p>')
  $skinsList.append($skinBlueLight)
```

----------------------------------------------
and then changed the things that needed changing (data-skin, skin names, name, some colors etc...)

### 7) If you want to remove any extra buttons from the main page, you will have to do so in the index file, depending what and where you want to remove/add.



