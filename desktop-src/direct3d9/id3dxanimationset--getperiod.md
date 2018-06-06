---
Description: Gets the period of the animation set.
ms.assetid: 0bb19ec1-c918-44b6-83b0-4fdbb4e1a485
title: ID3DXAnimationSet::GetPeriod method
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# ID3DXAnimationSet::GetPeriod method

Gets the period of the animation set.

## Syntax


```C++
DOUBLE GetPeriod();
```



## Parameters

This method has no parameters.

## Return value

Type: **[**DOUBLE**](https://msdn.microsoft.com/4553cafc-450e-4493-a4d4-cb6e2f274d46)**

Period of the animation set.

## Remarks

The period is the range of time that the animation key frames are valid. For looping animations, this is the period of the loop. The time units that the key frames are specified in (for example, seconds) is determined by the application.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx9anim.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXAnimationSet](id3dxanimationset.md)
</dt> </dl>

 

 



