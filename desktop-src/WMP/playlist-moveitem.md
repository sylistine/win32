---
title: Playlist.moveItem method
description: The moveItem method changes the location of an item in the playlist.
ms.assetid: f408c7a0-d1d6-4c0d-8ee5-0afd43b19a9d
keywords:
- moveItem method Windows Media Player
- moveItem method Windows Media Player , Playlist class
- Playlist class Windows Media Player , moveItem method
topic_type:
- apiref
api_name:
- Playlist.moveItem
api_location:
- wmp.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Playlist.moveItem method

The **moveItem** method changes the location of an item in the playlist.

## Syntax


```JScript
Playlist.moveItem(
  oldIndex,
  newIndex
)
```



## Parameters

<dl> <dt>

*oldIndex* \[in\]
</dt> <dd>

**Number** (**long**) containing the old index.

</dd> <dt>

*newIndex* \[in\]
</dt> <dd>

**Number** (**long**) containing the new index.

</dd> </dl>

## Return value

This method does not return a value.

## Remarks

Playlists stored in the library can change outside your control. Be sure to monitor and handle all appropriate playlist-related events so that the order of items in the playlist does not change unexpectedly.

To use this method, full access to the library is required. For more information, see [Library Access](library-access.md).

## Requirements



|                    |                                                                                    |
|--------------------|------------------------------------------------------------------------------------|
| Version<br/> | Windows Media Player version 7.0 or later.<br/>                              |
| DLL<br/>     | <dl> <dt>Wmp.dll</dt> </dl> |



## See also

<dl> <dt>

[**Playlist Object**](playlist-object.md)
</dt> <dt>

[**Settings.mediaAccessRights**](settings-mediaaccessrights.md)
</dt> <dt>

[**Settings.requestMediaAccessRights**](settings-requestmediaaccessrights.md)
</dt> </dl>

 

 




