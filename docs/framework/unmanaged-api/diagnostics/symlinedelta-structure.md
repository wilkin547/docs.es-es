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
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609305"
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
  
## <a name="see-also"></a>Consulta también

- [Estructuras de almacén de símbolos de diagnósticos](diagnostics-symbol-store-structures.md)
