# BundleFusion

![BundleFusion](img/teaser.jpg)

You are free to use this code with proper attribution in non-commercial applications (Please see [License.txt](License.txt)).

More information about this project can be found in our [paper](https://arxiv.org/pdf/1604.01093.pdf) and [project website](http://graphics.stanford.edu/projects/bundlefusion/).

## Apr. 25, 2018 Update - Build on VS2017 with CUDA9.1 for nVidia K2000
A few things you may have to do in order to compile:

- If you're running VS2017 with latest update, most likely you're using MSVC++ 14.14 _MSD_VER == 1914.
  In "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.1\include\crt>type host_config.h", modify _MSC_VER > 1911 to 1914
  
- Compile error "cannot include correct.h" etc. 
  Install Windows Universal CRT. Use Visaul Studio installer, choose "modify" for this additional package.
  
- Cannot find DX hearder even after installing DirectX SDK June 2010. 
  In Project Property VC++ Include Directory, add "\" between "{DXSDK_DIR}" and "Include"
  
- Error related to "std::enable_if" "xtr1common" blah blah.
  Turns out toolset 14.14 doesn't work well with CUDA9.1. Roll back to 14.11 works.
  Article on having two minor version of toolset by Microsoft:
    https://blogs.msdn.microsoft.com/vcblog/2017/11/15/side-by-side-minor-version-msvc-toolsets-in-visual-studio-2017/
	
- And here's a general guideline to build, which may or may not work for your system:
    https://bericht.neopostmodern.com/posts/artist-guide-to-bundlefusion

## Installation
The code was developed under VS2013, and tested with a Structure Sensor.

Requirements:
- DirectX SDK June 2010
- NVIDIA CUDA 7.0
- our research library mLib, a git submodule in external/mLib
- mLib external libraries can be downloaded [here](https://www.dropbox.com/s/fve3uen5mzonidx/mLibExternal.zip?dl=0)

Optional:
- Kinect SDK (2.0 and above)
- Prime sense SDK


## Citation:  
```
@article{dai2017bundlefusion,
  title={BundleFusion: Real-time Globally Consistent 3D Reconstruction using On-the-fly Surface Re-integration},
  author={Dai, Angela and Nie{\ss}ner, Matthias and Zoll{\"o}fer, Michael and Izadi, Shahram and Theobalt, Christian},
  journal={ACM Transactions on Graphics 2017 (TOG)},
  year={2017}
}
```

## Contact:
If you have any questions, please email Angela Dai at adai@cs.stanford.edu.



We are also looking for active participation in this open source effort making large-scale 3D scanning publically accessible. Please contact us :)
