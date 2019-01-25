---
title: COR_HEAPINFO (Estructura)
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffca8e076fe6fe966a9a07ed915a7e76ea06f37c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518077"
---
# <a name="corheapinfo-structure"></a>COR_HEAPINFO (Estructura)
Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` Si las estructuras de la colección de elementos no utilizados son válidas y se puede enumerar el montón; en caso contrario, `false`.|  
|`pointerSize`|El tamaño, en bytes, de punteros en la arquitectura de destino.|  
|`numHeaps`|El número de recolección de elementos lógicos montones en el proceso.|  
|`concurrent`|`TRUE` Si simultánea está habilitada la recolección de elementos (fondo); en caso contrario, `FALSE`.|  
|`gcType`|Un miembro de la [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeración que indica si el recolector de elementos no utilizados se ejecuta en una estación de trabajo o un servidor.|  
  
## <a name="remarks"></a>Comentarios  
 Una instancia de la `COR_HEAPINFO` estructura se devuelve mediante una llamada a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) método.  
  
 Antes de enumerar los objetos del montón de la colección de elementos no utilizados, debe comprobar siempre el `areGCStructuresValid` campo para asegurarse de que el montón está en un estado enumerable. Para obtener más información, consulte el [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
