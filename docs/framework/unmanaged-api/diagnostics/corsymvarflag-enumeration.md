---
description: 'Más información sobre: enumeración Corsymvarflag ('
title: CorSymVarFlag (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: 28f4b4775e20703e5dcaa7daf69affd3548aa3f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800466"
---
# <a name="corsymvarflag-enumeration"></a>CorSymVarFlag (Enumeración)

Indica si una variable es generada por el compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|Indica que la variable especificada es generada por el compilador.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de almacén de símbolos de diagnósticos](diagnostics-symbol-store-enumerations.md)
