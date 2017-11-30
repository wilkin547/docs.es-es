---
title: "CorSetENC (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSetENC
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSetENC
helpviewer_keywords: CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 85a909d92be8bfdb9ada709b54cf252183ff411e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corsetenc-enumeration"></a>CorSetENC (Enumeración)
Contiene valores que se usan para influir en el comportamiento durante la generación de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDSetENCOn`|Obsoleto.|  
|`MDSetENCOff`|Obsoleto.|  
|`MDUpdateENC`|Indica que mientras que se puedan actualizar los metadatos no se puede mover los símbolos (tokens).|  
|`MDUpdateFull`|Indica que se pueden mover tokens durante las actualizaciones.|  
|`MDUpdateExtension`|Indica que las actualizaciones pueden constar solo de adiciones. No se puede mover los símbolos (tokens).|  
|`MDUpdateIncremental`|Indica que la compilación es incremental.|  
|`MDUpdateDelta`|Indica que solo los metadatos modificados deben guardarse.|  
|`MDUpdateMask`|Incluye `MDUpdateENC`, `MDUpdateFull` y `MDUpdateIncremental`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
