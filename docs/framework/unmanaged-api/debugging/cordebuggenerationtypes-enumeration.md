---
description: 'Más información sobre: enumeración Cordebuggenerationtypes ('
title: CorDebugGenerationTypes (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
ms.openlocfilehash: f86b2bc9bf947c6b285c50678f46494005bb5537
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662135"
---
# <a name="cordebuggenerationtypes-enumeration"></a>CorDebugGenerationTypes (Enumeración)

Especifica la generación de una región de memoria en el montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a>Members  
  
|Nombre del miembro|Descripción|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|Generación 0.|  
|`CorDebug_Gen1`|Generación 1|  
|`CorDebug_Gen2`|Generación 2.|  
|`CorDebug_LOH`|Montón de objetos grandes.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
