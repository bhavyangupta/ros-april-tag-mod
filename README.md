april_tag [MODIFIED]
=========
This is a modified version of the original april_tag rosnode developed by 
palash : https://github.com/light-swarm/april_tag.
Following changes have been made:
1. Changed message structure. See "Output" below.
2. Messages are now published even if no tags are detected.
3. Default april tag size changed.
4. Default focal length of camera changed.

 Description:
=============
Detects 2D fiducial markers (april tags) from ros image stream and produces id, location and orientation of the tags. This ros node wraps the C++ April Tag library written by Michael Kaess and Hordur Johannson. April tags were developed by Edwin Olson. 

More on april tags here:
http://april.eecs.umich.edu/wiki/index.php/AprilTags

April Tags C++ library:
http://people.csail.mit.edu/kaess/apriltags/

Input:

`/camera/image_raw`

Output:

AprilTagList of structure:

````
Header header
int32 n_tags
AprilTag[]
````

Structure of each AprilTag:

```
uint32 	id
uint32 	hamming_distance
float64 distance
float64 x
float64 y
float64 z
float64 yaw
float64 pitch
float64 roll
```

distance,x,y,z are in cms. z is depth away from camera. x is horizontal with camera right as positive. 

Depends on: libeigen3-dev











