---
published: false
---


# ios Camera Feature using Ionic and Cordova #
This is a very quick example of a camera feature being implemented on an iphone even if you are a JavaScript developer.

_Warning: I am assuming readers are familiar with angular and/or ionic, but those with minor experience with the frameworks will also be able to follow along._

In order to interact the mobile devices native features we are using a platform know as cordova. More specifically we are going to use ngCordova which is a collection of AngularJS services and extensions created by Ionic and driven by the community. These services make it easier to integrate Cordova plugins into Ionic applications. I strongly recommend this tool when building hybrid application, it facilitates the process tremendously. So before we begin, make sure to install [ngCordova](http://ngcordova.com/) as a dependency.

Here is a quick overview
![Screen Shot 2016-01-11 at 5.22.13 PM.png]({{site.baseurl}}/images/Screen Shot 2016-01-11 at 5.22.13 PM.png)

In the above screen shot we inject [$cordovaCamera](http://ngcordova.com/docs/plugins/camera/) object into our CameraFactory, which will give us the funtionality needed to access the devices native camera feature.

First thing we do is declare the function takePhoto which will create the options object that will be passed into our call to the getPicture method on the $cordovaCamera object. The options object has many properties that you can fiddle with until you find a set up to meet your needs, you can find the definiton to each property [here](http://ngcordova.com/docs/plugins/camera/).

At the end our takePhoto funtion will return a call to the getPicture method because we want to make the data returned from it is available inside of our CameraController(below).






for example here in our camera feature we use cordova to capture the users current position and to activate the device's camera, allowing the user to take and share photos.
once the user is satisfied with the photo the have captured they the press the 'use photo' button and they are taken a new (window, view, or screen) where they can opt to add a filter to their image as well as add a comment.
After all of the customizations are made the user posts their image to the map for everyone in their area to enjoy
