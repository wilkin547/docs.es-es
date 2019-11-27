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
ms.openlocfilehash: a1e83e4b8cb6603029f3b42b1a3b9ba4810c9039
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438013"
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
  
## <a name="see-also"></a>Vea también

- [Estructuras de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
