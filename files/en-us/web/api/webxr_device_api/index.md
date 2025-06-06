---
title: WebXR Device API
slug: Web/API/WebXR_Device_API
page-type: web-api-overview
status:
  - experimental
browser-compat: api.Navigator.xr
spec-urls:
  - https://immersive-web.github.io/webxr/
  - https://immersive-web.github.io/anchors/
  - https://immersive-web.github.io/webxr-ar-module/
  - https://immersive-web.github.io/depth-sensing/
  - https://immersive-web.github.io/dom-overlays/
  - https://immersive-web.github.io/webxr-gamepads-module/
  - https://immersive-web.github.io/webxr-hand-input/
  - https://immersive-web.github.io/hit-test/
  - https://immersive-web.github.io/layers/
  - https://immersive-web.github.io/lighting-estimation/
---

{{DefaultAPISidebar("WebXR Device API")}}{{SecureContext_Header}}{{SeeCompatTable}}

**WebXR** is a group of standards which are used together to support rendering 3D scenes to hardware designed for presenting virtual worlds (**virtual reality**, or **VR**), or for adding graphical imagery to the real world, (**augmented reality**, or **AR**). The **WebXR Device API** implements the core of the WebXR feature set, managing the selection of output devices, render the 3D scene to the chosen device at the appropriate frame rate, and manage motion vectors created using input controllers.

WebXR-compatible devices include fully-immersive 3D headsets with motion and orientation tracking, eyeglasses which overlay graphics atop the real-world scene passing through the frames, and handheld mobile phones which augment reality by capturing the world with a camera and augment that scene with computer-generated imagery.

To accomplish these things, the WebXR Device API provides the following key capabilities:

- Find compatible VR or AR output devices
- Render a 3D scene to the device at an appropriate frame rate
- (Optionally) mirror the output to a 2D display
- Create vectors representing the movements of input controls

At the most basic level, a scene is presented in 3D by computing the perspective to apply to the scene in order to render it from the viewpoint of each of the user's eyes by computing the position of each eye and rendering the scene from that position, looking in the direction the user is currently facing. Each of these two images is rendered into a single framebuffer, with the left eye's rendered image on the left and the right eye's viewpoint rendered into the right half of the buffer. Once both eyes' perspectives on the scene have been rendered, the resulting framebuffer is delivered to the WebXR device to be presented to the user through their headset or other appropriate display device.

While the older [WebVR API](/en-US/docs/Web/API/WebVR_API) was designed solely to support Virtual Reality (VR), WebXR provides support for both VR and Augmented Reality (AR) on the web. Support for AR functionality is added by the WebXR Augmented Reality Module.

A typical XR device can have either 3 or 6 degrees of freedom and might or might not have an external positional sensor.

The equipment may also include an accelerometer, barometer, or other sensors which are used to sense when the user moves through space, rotates their head, or the like.

## WebXR reference docs

<div class="index">

### Initialization

- {{domxref("navigator.xr")}}
- {{domxref("XRSystem")}}
- {{domxref("XRPermissionStatus")}}
- `Permissions-Policy`: [`xr-spatial-tracking`](/en-US/docs/Web/HTTP/Reference/Headers/Permissions-Policy/xr-spatial-tracking)

### Session

- {{DOMxRef("XRSession")}}
- {{domxref("XRSessionEvent")}}
- {{DOMxRef("XRRenderState")}}

### Frame loop

- {{DOMxRef("XRFrame")}}

### Spaces

- {{DOMxRef("XRSpace")}}
- {{DOMxRef("XRReferenceSpace")}}
- {{DOMxRef("XRBoundedReferenceSpace")}}
- {{domxref("XRReferenceSpaceEvent")}}
- {{domxref("XRJointSpace")}}

### Views

- {{DOMxRef("XRView")}}
- {{DOMxRef("XRViewport")}}

### Geometric primitives

- {{DOMxRef("XRRigidTransform")}}

### Pose

- {{DOMxRef("XRPose")}}
- {{DOMxRef("XRJointPose")}}
- {{DOMxRef("XRViewerPose")}}

### Input

- {{DOMxRef("XRHand")}}
- {{DOMxRef("XRInputSource")}}
- {{DOMxRef("XRInputSourceArray")}}
- {{domxref("XRInputSourceEvent")}}
- {{domxref("XRInputSourcesChangeEvent")}}

### Layers

- {{DOMxRef("XRLayer")}}
- {{DOMxRef("XRLayerEvent")}}
- {{DOMxRef("XRCompositionLayer")}}
- {{DOMxRef("XRCubeLayer")}}
- {{DOMxRef("XRCylinderLayer")}}
- {{DOMxRef("XREquirectLayer")}}
- {{DOMxRef("XRProjectionLayer")}}
- {{DOMxRef("XRQuadLayer")}}
- {{DOMxRef("XRMediaBinding")}}

### WebGL binding

- {{DOMxRef("XRWebGLBinding")}}
- {{domxref("WebGLRenderingContext.makeXRCompatible()")}}
- {{DOMxRef("XRWebGLLayer")}}
- {{DOMxRef("XRSubImage")}}
- {{DOMxRef("XRWebGLSubImage")}}

### Anchors

- {{domxref("XRAnchor")}}
- {{domxref("XRAnchorSet")}}

### Depth sensing

- {{domxref("XRDepthInformation")}}
- {{domxref("XRCPUDepthInformation")}}
- {{domxref("XRWebGLDepthInformation")}}

### Hit testing

- {{domxref("XRHitTestSource")}}
- {{domxref("XRTransientInputHitTestSource")}}
- {{domxref("XRHitTestResult")}}
- {{domxref("XRTransientInputHitTestResult")}}
- {{domxref("XRRay")}}

### Lighting estimation

- {{domxref("XRLightEstimate")}}
- {{domxref("XRLightProbe")}}

</div>

## Guides and tutorials

The following guides and tutorials are a great resource to learn how to comprehend WebXR and the underlying 3D and VR/AR graphics concepts.

<div class="index">

### Foundations and basics

- [Fundamentals of WebXR](/en-US/docs/Web/API/WebXR_Device_API/Fundamentals)
- [Matrix math for the web](/en-US/docs/Web/API/WebGL_API/Matrix_math_for_the_web)
- [WebXR application life cycle](/en-US/docs/Web/API/WebXR_Device_API/Lifecycle)

### Creating a mixed reality experience

- [Starting up and shutting down a WebXR session](/en-US/docs/Web/API/WebXR_Device_API/Startup_and_shutdown)
- [Geometry and reference spaces in WebXR](/en-US/docs/Web/API/WebXR_Device_API/Geometry)
- [Spatial tracking in WebXR](/en-US/docs/Web/API/WebXR_Device_API/Spatial_tracking)
- [Rendering and the WebXR frame animation callback](/en-US/docs/Web/API/WebXR_Device_API/Rendering)
- [Viewpoints and viewers: Simulating cameras in WebXR](/en-US/docs/Web/API/WebXR_Device_API/Cameras)
- [A perspective retrospective for WebXR developers](/en-US/docs/Web/API/WebXR_Device_API/Perspective)
- [Lighting a WebXR setting](/en-US/docs/Web/API/WebXR_Device_API/Lighting)
- [Using bounded reference spaces](/en-US/docs/Web/API/WebXR_Device_API/Bounded_reference_spaces)

### Making it interactive

- [Movement, orientation, and motion: A WebXR example](/en-US/docs/Web/API/WebXR_Device_API/Movement_and_motion)
- [Inputs and input sources](/en-US/docs/Web/API/WebXR_Device_API/Inputs)
- [Targeting and hit detection](/en-US/docs/Web/API/WebXR_Device_API/Targeting)

### Performance and security

- [WebXR performance guide](/en-US/docs/Web/API/WebXR_Device_API/Performance)
- [Permissions and security for WebXR](/en-US/docs/Web/API/WebXR_Device_API/Permissions_and_security)

</div>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Drawing graphics](/en-US/docs/Learn_web_development/Extensions/Client-side_APIs/Drawing_graphics)
- [WebGL API](/en-US/docs/Web/API/WebGL_API): Accelerated 2D and 3D graphics on the web
- [Canvas API](/en-US/docs/Web/API/Canvas_API): 2D drawing for the web
- [Canvas tutorial](/en-US/docs/Web/API/Canvas_API/Tutorial)
