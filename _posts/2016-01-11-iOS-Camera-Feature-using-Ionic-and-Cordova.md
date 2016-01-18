---
published: false
---




#Cordova Camera and Ionic#



This is a very quick example of a camera feature being implemented on an iPhone even if you are a JavaScript developer.

_Warning: I am assuming readers are familiar with angular and/or ionic, but those with minor experience with the frameworks will also be able to follow along._

In order to interact the mobile devices native features we are using a platform know as Cordova. More specifically we are going to use ngCordova which is a collection of AngularJS services and extensions created by Ionic and driven by the community. These services make it easier to integrate Cordova plugins into Ionic applications. I strongly recommend this tool when building hybrid application, it facilitates the process tremendously. So before we begin, make sure to install [ngCordova](http://ngcordova.com/) as a dependency.

#Here is a quick overview of a portion of our factory:#

![Screen Shot 2016-01-11 at 5.22.13 PM.png]({{site.baseurl}}/images/Screen Shot 2016-01-11 at 5.22.13 PM.png)

In the above screen shot we inject [$cordovaCamera](http://ngcordova.com/docs/plugins/camera/) object into our CameraFactory, which will give us the functionality needed to access the devices native camera feature.

First thing we do is declare the function takePhoto which will create the options object that will be passed into our call to the getPicture method on the $cordovaCamera object. The options object has many properties that you can fiddle with until you find a set up to meet your needs, you can find the definition to each property [here](http://ngcordova.com/docs/plugins/camera/).

At the end our takePhoto function will return a call to the getPicture method because we want to make the data returned from it is available inside of our CameraController(below).

The getPicture method prompts the user to take a picture with their devices native camera. This is due to the fact that we set the sourceType property on the options object to have a value of Camera.PictureSourceType.CAMERA.

# Inside of CameraController:#
 
![Screen Shot 2016-01-14 at 3.38.25 PM.png]({{site.baseurl}}/images/Screen Shot 2016-01-14 at 3.38.25 PM.png)

Up above we have CameraController which we injected with CameraFactory a few lines before the screenshot. What we are doing on line 24 is creating a function called takePicture on scope with the sole purpose of calling the takePhoto function from the CameraFactory and handling the data that it returns. 

On line 26 we have a then statement that receives the imageData returned by the call to $cordovaCamera's getPicture method. This data is called a 64base encoded string containing all of the pixel information for the image capture by the user. We prefix that string with 'data:image/jpeg;base64,' and this allows us to use img HTML tags to render the users image to any view.


#**Bonus!!!**#

Starting on line 36 we have an event listener for when we enter the view the Camera controller is attached to. Inside of the event listener we perform tasks that we want to automatically occur when the user goes to the camera view. Line 39 invokes the takePicture function which will prompt the user to that a picture through the process explained above. This removes the need for another button click for the user to take a picture thus reducing friction and creating a more intuitive user experience.
