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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d98ebed2eb853d5dc8177b0b044bf654c3978494
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744350"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA (Estructura)
Proporciona información al controlador de símbolos acerca de los métodos que se movieron como resultado de las modificaciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`mdMethod`|Token de metadatos del método.|  
|`delta`|El número de líneas que se ha movido el método.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl  
  
## <a name="see-also"></a>Vea también

- [Estructuras de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
