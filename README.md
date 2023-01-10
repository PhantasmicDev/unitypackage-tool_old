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

## Usage
### Packing
Packing a repo that follows [Unity's package layout](https://docs.unity3d.com/Manual/cus-layout.html):

```yaml
- uses: PhantasmicDev/unitypackage-packer@v1
  with:
      command: "pack"
      package: "my-package.unitypackage"
      
      # In this example the workspace directory is considered the 'com.organization.package' directory and 
      # for Unity to extract our directory inside the 'Packages' folder, we map our workspace directory to
      # the target path 'Packages/{desired package directory name}'.
      pack-map: |
        {
          "${{ github.workspace }}" : "Packages/com.phantasmicdev.mycoolpackage"
        }
```
