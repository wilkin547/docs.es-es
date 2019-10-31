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
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132332"
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
|`areGCStructuresValid`|`true` si las estructuras de recolección de elementos no utilizados son válidas y se puede enumerar el montón; de lo contrario, `false`.|  
|`pointerSize`|Tamaño, en bytes, de los punteros en la arquitectura de destino.|  
|`numHeaps`|El número de montones de recolección de elementos no utilizados lógicas en el proceso.|  
|`concurrent`|`TRUE` si la recolección de elementos no utilizados simultánea (en segundo plano) está habilitada; de lo contrario, `FALSE`.|  
|`gcType`|Miembro de la enumeración [cordebuggctype (](cordebuggctype-enumeration.md) que indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.|  
  
## <a name="remarks"></a>Comentarios  
 Se devuelve una instancia de la estructura `COR_HEAPINFO` llamando al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .  
  
 Antes de enumerar los objetos en el montón de recolección de elementos no utilizados, debe comprobar siempre el campo `areGCStructuresValid` para asegurarse de que el montón se encuentra en un estado Enumerable. Para obtener más información, vea el método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
