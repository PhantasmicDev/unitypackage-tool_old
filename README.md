# UnityPackage Packer

An action that allows packing and unpacking Unity [asset packages](https://docs.unity3d.com/Manual/AssetPackages.html) without the Unity editor or Unity project folder. 

This action leverages [unity-packer by MirageNet](https://github.com/MirageNet/unity-packer), a fork of [UnityPackager by TwoTenPvP](https://github.com/TwoTenPvP/UnityPackager), to pack or unpack the .unitypackage files.

## Inputs

```yaml

- uses: PhantasmicDev/unitypackage-packer@v1
  with:
    # Either 'pack' or 'unpack'.
    command: ''
    
    # If packing, this is the package that will be generated, must end with '.unitypackage'. 
    # If unpacking this is the '.unitypackage' to extract.
    package: ''
    
    # Json key value pair entries, the key being the file/directory to pack and the value being the target path within the package.
    pack-map: ''
    
    # The location where the '.unitypackage' content will be extracted to when unpacking.
    output-path: ''

```
