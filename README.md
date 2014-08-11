I2OAudioStreamPlayer
===================

Why this Class when there is AVPlayer and AVPlayerItem?
In an ideal world, you have fast uninterrupted internet connection.
Not where I live. 
Here Internet slows and just drops dead for minutes.
Just instantiating objects from AVPlayer and AVPlayerItem and saying "ok, now go Play", doesnt cut it in the real
world.

How can your audio player then behave gracefully and be social with the user? 
By first knowing what's going with the AVfoundation objects, the player buffer and the internet.
Then informing the users what`s going on....in their language ofcourse.
To accomplish this the objects in the App need to know what they need to know and communicate to other objects what they need to know.

To allow easy scalability this Class is loosely coupled with the View Controller it is created by. 
Leaving the View Controller to do View updates. This is done by sending messages to the View Controller.
KVO and NSNotification are used for this purpose.




*** this Class is being updated. It will be available middle of August'14