# Introduction

This is a C++ implementation of OpenTLD that was originally published in MATLAB by Zdenek Kalal and is also forked from gnebehay
This project is used in MACX and XCode.
You need have XCode and OpenCV. 

# Building
## Dependencies
* OpenCV
* CMake (optional)
* libconfig++ (optional)
* Qt4 (optional)

If you just want to run it, you need to 
* add your OpenCV lib into this project.
* add libconfig++.a, libcvblobs.a, libmain.a and libopentld.a into this project. You can find them in "./lib/"
* find "Library Search Paths" in "Build Settings" and then add "/usr/local/lib", "../lib"
* add "/usr/local/include /usr/local/include/opencv ./libopentld/imacq ./libopentld/mftracker ./libopentld/tld ./src/3rdparty/libconfig" into "Header Search Paths".

If you want to compile by yourself, you need to do as follow:
* `brew install python`
* `brew install gfortran`
* `easy_install numpy`
* `brew install cmake`
* `brew install opencv`
* `cmake` build the project
* `make


## Keyboard shortcuts

* `q` quit
* `b` remember current frame as background model / clear background
* `c` clear model and stop tracking  git
* `l` toggle learning
* `a` toggle alternating mode (if true, detector is switched off when tracker is available)
* `e` export model to file specified in configuration parameter "modelExportFile"
* `i` import model from file specified in configuration parameter "modelPath"
* `r` clear model, let user reinit tracking

## Command line options
### Synopsis
`opentld [option arguments] [arguments]`

### option arguments
* `[-a <startFrameNumber>]` video starts at the frameNumber _startFrameNumber_
* `[-b <x,y,w,h>]` Initial bounding box
* `[-d <device>]` select input device: _device_=(IMGS|CAM|VID|STREAM)  
	_IMGS_: capture from images  
	_CAM_: capture from connected camera  
	_VID_: capture from a video  
	_STREAM_: capture from RTSP stream
* `[-e <path>]` export model after run to _path_
* `[-f]` shows foreground
* `[-i <path>]` _path_ to the images or to the video.
* `[-j <number>]` show trajectory for the last _number_ frames
* `[-h]` shows help
* `[-m <path>]` if specified load a model from _path_. An initialBoundingBox must be specified or selectManually must be true.
* `[-n <number>]` Specifies the video device to use (defaults to 0). Useful to select a different camera when multiple cameras are connected.
* `[-p path]` prints results into the file _path_
* `[-s]` if set, user can select initial bounding box
* `[-t <theta>]` threshold for determining positive results
* `[-z <lastFrameNumber>]` video ends at the frameNumber _lastFrameNumber_.
	If _lastFrameNumber_ is 0 or the option argument isn't specified means
	all frames are taken.

### Arguments
`[CONFIG_FILE]` path to config file
