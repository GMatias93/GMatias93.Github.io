---
published: false
---

# ios Camera Feature using Ionic and Cordova #
This is a very quick example of a camera feature being implemented on an iphone even if you are a JavaScript developer. 

_Warning: I am assuming readers are familiar with angular and/or ionic, but those with minor experience with the frameworks will also be able to follow along._

In order to interact the mobile devices native features we are using a platform know as cordova. More specifically we are going to use ngCordova which is a collection of AngularJS services and extensions created by Ionic and driven by the community. These services make it easier to integrate Cordova plugins into Ionic applications. I strongly recommend this tool when building hybrid application, it facilitates the process tremendously.

Here is a quick overview  
![Screen Shot 2016-01-11 at 5.22.13 PM.png]({{site.baseurl}}/_posts/Screen Shot 2016-01-11 at 5.22.13 PM.png)





for example here in our camera feature we use cordova to capture the users current position and to activate the device's camera, allowing the user to take and share photos.
once the user is satisfied with the photo the have captured they the press the 'use photo' button and they are taken a new (window, view, or screen) where they can opt to add a filter to their image as well as add a comment.
After all of the customizations are made the user posts their image to the map for everyone in their area to enjoy
