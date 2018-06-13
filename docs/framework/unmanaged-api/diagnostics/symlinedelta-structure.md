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
ms.openlocfilehash: 77cd8b7d791d11f6d40386f4747c60cd4832521a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428099"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA (Estructura)
Proporciona información al controlador de símbolos sobre métodos que se movieron como resultado de modificaciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`mdMethod`|Símbolo (token) de metadatos del método.|  
|`delta`|El número de líneas que se ha movido el método.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
