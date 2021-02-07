---
description: 'Más información acerca de: estructura SYMLINEDELTA ('
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
ms.openlocfilehash: ae00d2be9809b48180d2cd99d05e410624033419
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761452"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`mdMethod`|Token de metadatos del método.|  
|`delta`|Número de líneas que se ha despasado el método.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl  
  
## <a name="see-also"></a>Vea también

- [Estructuras de almacén de símbolos de diagnósticos](diagnostics-symbol-store-structures.md)
