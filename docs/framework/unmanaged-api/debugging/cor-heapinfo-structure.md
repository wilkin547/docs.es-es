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
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179308"
---
# <a name="cor_heapinfo-structure"></a>COR_HEAPINFO (Estructura)
Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es enumerable.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`si las estructuras de recolección de elementos no utilizados son válidas y se puede enumerar el montón; de `false`lo contrario, .|  
|`pointerSize`|El tamaño, en bytes, de los punteros en la arquitectura de destino.|  
|`numHeaps`|El número de montones lógicos de recolección de elementos no utilizados en el proceso.|  
|`concurrent`|`TRUE`si la recolección simultánea (de fondo) de elementos no utilizados está habilitada; de `FALSE`lo contrario, .|  
|`gcType`|Miembro de la [enumeración CorDebugGCType](cordebuggctype-enumeration.md) que indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.|  
  
## <a name="remarks"></a>Observaciones  
 Se devuelve `COR_HEAPINFO` una instancia de la estructura mediante una llamada a la [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) método.  
  
 Antes de enumerar objetos en el montón `areGCStructuresValid` de recolección de elementos no utilizados, siempre debe comprobar el campo para asegurarse de que el montón está en un estado enumerable. Para obtener más información, vea el [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
