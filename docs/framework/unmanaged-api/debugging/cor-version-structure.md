---
title: COR_VERSION (Estructura)
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
ms.openlocfilehash: 874c0520482cc5a3bbfcdd17924edee84fe91ff5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675326"
---
# <a name="cor_version-structure"></a>COR_VERSION (Estructura)

Almacena la versión estándar en cuatro partes de Common Language Runtime.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`dwMajor`|Número de versión principal.|  
|`dwMinor`|Número de versión secundaria.|  
|`dwBuild`|Número de compilación.|  
|`dwSubBuild`|Número de la subcompilación.|  
  
## <a name="remarks"></a>Comentarios  

 Si el número de versión es 1.0.3705.288, 1 es el número de versión principal, 0 es el número de versión secundaria, 3705 es el número de compilación y 288 es el número de la subcompilación.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
