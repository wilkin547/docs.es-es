---
title: SYMLINEDELTA (Estructura)
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690946"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA (Estructura)

Proporciona información al controlador de símbolos sobre los métodos que se movieron como resultado de las ediciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`mdMethod`|Token de metadatos del método.|  
|`delta`|Número de líneas que se ha despasado el método.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de almacén de símbolos de diagnósticos](diagnostics-symbol-store-structures.md)
