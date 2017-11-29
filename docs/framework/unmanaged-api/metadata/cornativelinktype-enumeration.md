---
title: "CorNativeLinkType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkType
helpviewer_keywords: CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8da034590bc5e0b2cbd9456d9d5b4ef4970f259
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cornativelinktype-enumeration"></a>CorNativeLinkType (Enumeración)
Proporciona valores que indican el tipo vinculado en código nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`nltNone`|Indica que no se especifica ninguna de las palabras clave.|  
|`nltAnsi`|Indica que se ha especificado una palabra clave ANSI.|  
|`nltUnicode`|Indica que se ha especificado una palabra clave Unicode|  
|`nltAuto`|Indica que se ha especificado una palabra clave auto.|  
|`nltOle`|Indica que se ha especificado una palabra clave OLE.|  
|`nltMaxValue`|No usado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
