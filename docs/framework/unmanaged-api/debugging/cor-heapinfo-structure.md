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
ms.openlocfilehash: f7b340a73aa9eaebca9c0d78563ae298557039b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274191"
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`Si las estructuras de recolección de elementos no utilizados son válidas y se puede enumerar el montón; en caso `false`contrario,.|  
|`pointerSize`|Tamaño, en bytes, de los punteros en la arquitectura de destino.|  
|`numHeaps`|El número de montones de recolección de elementos no utilizados lógicas en el proceso.|  
|`concurrent`|`TRUE`Si la recolección de elementos no utilizados simultánea (en segundo plano) está habilitada; en caso `FALSE`contrario,.|  
|`gcType`|Miembro de la enumeración [cordebuggctype (](cordebuggctype-enumeration.md) que indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.|  
  
## <a name="remarks"></a>Comentarios  
 Se devuelve una instancia `COR_HEAPINFO` de la estructura llamando al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .  
  
 Antes de enumerar los objetos en el montón de recolección de elementos no utilizados `areGCStructuresValid` , debe comprobar siempre el campo para asegurarse de que el montón se encuentra en un estado Enumerable. Para obtener más información, vea el método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
