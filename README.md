# Sins Tutorial

Sins provides a full pipeline which is easy to use.
Here are some tutorials about how to use the plugins in each dcc.

[Hiero](hiero/readme.md)
[Maya](maya/readme.md)
[Nuke](nuke/readme.md)
[Houdini](houdini/readme.md)
[Katana](katana/readme.md)
[RV](rv/readme.md)
[Blender](blender/readme.md)
[Unreal](unreal/readme.md)


Here's a complete workflow of the process from asset modeling to shot comp.

* Asset level
    * Create assets and variants.
    * Model in maya, [Create and switch variants](maya/readme.md#create-and-switch-variants) and [Submit playblast](maya/readme.md#playblast).
      After review pass, [Submit mod](maya/readme.md#mod). You can also use usd to combine an asset based on components.
      Before this, you may [Export component](maya/readme.md#component).
    * Do rigging and [Submit rig](maya/readme.md#rig).
    * [Import mod in katana](katana/readme.md#initialize). 
      Do lookdev and [Export lookfile in katana](katana/readme.md#publish-lookdev).
      The usd material can be view in maya via GL(Hydra) viewport. If you use arnold for material, it can also be seen in Arnold(Hydra).
    * [Import mod usd in maya](maya/readme.md#usd-tools) and do layout for set asset.
      For some asset, you may need to [Do layout in houdini](houdini/readme.md), for easy instance work.
* Shot level
    * Create project and sequences. [Create shots and import storyboard reference in hiero](hiero/readme.md#import-shots).
    * [Create usd shots](maya/readme.md#create-usd-shots).
    * [Do layout for base shot and submit](maya/readme.md#usd-tools).
    * [Initialize scene in maya](maya/readme.md#initialize).
    * [Import rig](maya/readme.md#import-rig-as-reference), do camera animation, then [Submit playblast](maya/readme.md#playblast).
    * After review pass, [Submit camera](maya/readme.md#cam). 
      If you do some layout overrides in the scene, need to [Submit shot layout](maya/readme.md#usd-push).
      If you do asset animation, need to [Submit shot animation](maya/readme.md#ani).
      You can do layout and camera in lay step task and do animation in ani step task, or both in same step task. Sins doesn't have limitation about this.
    * [Initializate scene in houdini](houdini/readme.md#initialize).
    * Do pyro or dynamic simulation in houdini and [Submit flipbook](houdini/readme.md).
    * After review pass, [Export and submit efx cache](houdini/readme.md).
    * [Import pre-lgt in katana](maya/readme.md#import-shots) and do lighting. [Render from katana](katana/readme.md#render).
      You can also [Export light from katana](katana/readme.md#publish-light), which can be used in maya and view.
    * [Import lgt images in nuke](nuke/readme.md) and do comp. [Render from nuke](nuke/readme.md) and [Submit](nuke/readme.md).
    * After any versions submit to Sins, you can [Review in rv](rv/readme.md).

