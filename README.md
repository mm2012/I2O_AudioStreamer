I2OAudioStreamPlayer
===================

Problem:
Why not just use AVPlayer and AVPlayerItem?
In an ideal world, you have fast uninterrupted internet connection. But not where I live. 
Here Internet slows and just drops dead for minutes.
The complexity of real life environment means it doesn't cut it to just create AVPlayer and AVPlayerItem objects and then telling them "ok, now go Play".

Solution:
The streaming audio player must behave gracefully and be social with the user.
How? 
By first knowing what's going with the AVfoundation objects, the player buffer and Network connectivity.
Then informing the users of what`s going on....in their language ofcourse.
To accomplish this the objects in the App need to know what they need to know and communicate to other objects what they need to know.

Implementation:
This Stream Player audio player, to allow scalability, is loosely coupled with the View Controller. 
The View Controller creates this Stream Player Object hence owns it too. The Stream Player interacts with the View Controller via Delegation. 
Responsibility of UI updates are delegated to the View Controller. 
The I2OStreamPlayer is very chatty. It communicates to the View Controller via Delegation asking for UI updates and informing of Playback Buffer status.

KVO, NSNotification and Delegation are used for this purpose.
The Stream Player uses Key-Value-Observing to monitor state change in the key values of the AVPlayerItem.

*** this Class is being updated. It will be available middle of August'14