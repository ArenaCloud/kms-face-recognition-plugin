# Face Recognition Filter

Filter which recognizing faces in real time implemented as a Kurento OpenCV Filter.

## Prerequisites

 * CMake 2.x+
 * Kurento Media Server 6.x
 * [face_rec library](https://github.com/sping/face-recognition-lib) 
 
## Linking face_rec library

Make a symbolic link from the face_rec library to /src/server/implementation/objects/face_rec:

```
└── src
    └── server
        ├── implementation
        │   └── objects
        │       └── face_rec -> FACE_REC_LIB_PATH
        └── interface
```
where FACE_REC_LIB_PATH is the path to the face_rec directory. 

In the case of confusion just look at /src/server/CMakeLists.txt

The library has to be linked/copied to the said destination because absolute paths did not work correctly using the
given CMake process which transformed the absolute paths to relative paths at the part where the Module is compiled.







