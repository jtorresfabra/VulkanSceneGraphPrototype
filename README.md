VulkanSceneGraphPrototype (VSG) is a prototype for a modern, cross platform, high performance scene graph library built upon Vulkan graphics/compute API.  The software is written in C++17, and follows the [CppCoreGuidlines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines) and [FOSS Best Practices](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md).  The source code is published under the [MIT License](LICENSE.md).

This repository contains basic documentation, C++ headers and source and CMake build scripts to build the prototype libvsg library.  Additional support libraries and examples are provided in separate repositories, links to these provided below.  The software currently builds under Linux and Windows.  We plan on providing support for Android by the end of 2018, and later add OSX and iOS support using [MoltenVk](https://github.com/KhronosGroup/MoltenVK).

The VulkanSceneGraphPrototype is the precursor to final VulkanSceneGraph/VkSceneGraph project, the prototype will be developed through to the end of 2018, then in 2019 we'll begin work on the final project that will be appropriate for use within user compute and graphics middle-ware and applications.


## Useful links within the codebase
* Detailed build and install [instructions](INSTALL.md)
* Software development [Road Map](ROADMAP.md)
* Design : [Principles and Philosophy](docs/Design/DesignPrinciplesAndPhilosophy.md),  [High Level Decisions](docs/Design/HighLevelDesignDecisions.md)
* Community resources :  [Code of Conduct](docs/CODE_OF_CONDUCT.md), [Contributing guide](docs/CONTRIBUTING.md)
* Exploration Phase Materials : [Areas of Interest](docs/ExplorationPhase/AreasOfInterest.md), [3rd Party Resources](docs/ExplorationPhase/3rdPartyResources.md) and [Exploration Phase Report](docs/ExplorationPhase/VulkanSceneGraphExplorationPhaseReport.md)
* Headers - the public interface : [include/vsg/](include/vsg)
* Source - the implementation : [src/vsg/](src/vsg)

---


## Quick Guide to building the VSG

### Prerequisites:
* C++17 compliant compiler i.e.. g++ 7.3 or later, Clang 6.0 or later, Visual Studio S2017 or later.
* [Vulkan](https://vulkan.lunarg.com/) 1.1 or later.
* [CMake](https://www.cmake.org) 3.5 or later.
* [GLFW](https://www.glfw.org)  3.3 or later.  The plan is to implement native Windowing support so this dependency will
 later be removed.

The above dependency versions are known to work so they've been set as the current minimum, it may be possible to build against older versions.  If you find success with older versions let us know and we can update the version info.

### Command line build instructions:
To build and install the static libvsg library (.a/.lib) in source:

    git clone https://github.com/robertosfield/VulkanSceneGraphPrototype.git
    cd VulkanSceneGraphPrototype
    cmake .
    make -j 8
    make install

Full details on how to build of the VSG can be found in the [INSTALL.md](INSTALL.md) file.

---

## Examples of VSG in use

It's still very early days for the project so we don't have many projects that use to the VSG to reference, for our own testing purposes we have two project which may serve as an illustration of how to compile against the VSG and how to use parts of it's API.  These projects are:

* [osg2vsg](https://github.com/robertosfield/osg2vsg) utility library that integrates OpenSceneGraph with the VSG to leverages data and image loaders.
* [vsgExamples](https://github.com/robertosfield/vsgExamples) example programs that we are using to test out VSG functionality and illustrates usage.

Three examples within the vsgExamples project that may be of particular interest are ports of Vulkan tutorials to the VSG API.  In each case the VSG version requires less than 1/5th the amount of code to achieve the same functionality.

* [Vulkan Tutorial](https://vulkan-tutorial.com/) ported as [vsgExamples/examples_osg2vsg/vsgdraw](https://github.com/robertosfield/vsgExamples/blob/master/examples_osg2vsg/vsgdraw/vsgdraw.cpp)
* Version of vsgdraw using vkPushConstants [vsgExamples.examples_osg2vsg/vsgpushconstants](https://github.com/robertosfield/vsgExamples/blob/master/examples_osg2vsg/vsgpushconstants/vsgpushconstants.cpp)
* [vulkan_minimal_compute](https://github.com/Erkaman/vulkan_minimal_compute) tutorial ported to VSG [vsgExamples/examples_osg2vsg/vsgcompute](https://github.com/robertosfield/vsgExamples/blob/master/examples_osg2vsg/vsgcompute/vsgcompute.cpp)

