---
title: CorDebugGCType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
ms.openlocfilehash: 6b3075613af0403527ecf67d574c0f5733a5cd8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712617"
---
# <a name="cordebuggctype-enumeration"></a>CorDebugGCType (Enumeración)

Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a>Parámetros  
  
## <a name="members"></a>Miembros  
  
|Nombre del miembro|Descripción|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|El recolector de elementos no utilizados se está ejecutando en una estación de trabajo.|  
|`CorDebugServerGC`|El recolector de elementos no utilizados se está ejecutando en un servidor.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones de depuración](debugging-enumerations.md)
