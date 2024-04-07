# Disciples III Tool

dis3tool is utility tool to convert Disciples III texture, geomtry and animation resources.

## Download

[version 1.0.0](https://github.com/rootext/dis3tool-release/releases/download/v1.0.0/dis3tool-1.0.0.zip)

## Features
* Convert between DIII texture `*.t` and DDS texture `*.dds `
* Convert between DIII static geometry `*.g` and glTF format `*.gltf`
* Convert between DIII scene `*.scene` and glTF format `*.gltf`
* Extract `*.vdpack` and `*.vdpatch` files
* Bulk conversion
* Scale DIII geometry

## Supported versions
* [Disciples III: Renaissance](https://en.wikipedia.org/wiki/Disciples_III:_Renaissance#Renaissance)
* [Disciples_III: Resurrection](https://en.wikipedia.org/wiki/Disciples_III:_Renaissance#Resurrection)
* [Disciples_III: Reincarnation](https://en.wikipedia.org/wiki/Disciples_III:_Renaissance#Reincarnation)

## Formats

### `*.vdpack` and `*.vdpatch`

|type|name|repeat|description|
|---|---|---|---|
|file|
|u32|count|1|number of resources|
|item[]|items|count|resources|
|item|
|string|name|1|file name of resource
|u32|size|1|size of resource in bytes|
|u32|offset|1|offset of resource data in bytes from beggining of file|
|u32|flags|1|flags, usually 0|
|string|
|u32|length|1|length of string including zero|
|u8[]|value|length|string value in UTF-8|
|u8|zero|1|zero|

### `*.t`

|type|name|repeat|description|
|---|---|---|---|
|file|
|header|header|1|texture metadata|
|u8[]|data|till eof|texture data|
|header (59 bytes)|
|u32|-|1||
|u32|type|1|texture type|
||||1=R5G6B5<br/> 2=A4R4G4B4<br/> 3=A1R5G5B5<br/> 4=R8G8B8<br/> 5=A8R8G8B8<br/> 6=DXT1<br/> 7=DXT3<br/> 8=DXT5|
|u32|-|1||
|u32|mipmap|1|number of mipmaps|
|u32|width|1|texture width|
|u32|height|1|texture height|
|u32|-|1||
|u8[]|-|3||
|u32|-|1||
|u32|-|1||
|u32|-|1||
|u32|frames|1|number of frames|
|u32|-|1||
|u32|signature|1|0x41700000|
|u32|-|1||



 _copyright 2024 root.ext@gmail.com_

