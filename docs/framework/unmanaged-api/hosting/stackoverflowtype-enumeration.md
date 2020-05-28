---
title: StackOverflowType (Enumeración)
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
ms.openlocfilehash: f399d33dbe05cb5768aa45533ef30d28409e18e2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006485"
---
# <a name="stackoverflowtype-enumeration"></a>StackOverflowType (Enumeración)
Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`SO_ClrEngine`|El motor de ejecución produjo el desbordamiento de pila.|  
|`SO_Managed`|El desbordamiento de pila se produjo por código administrado.|  
|`SO_Other`|El desbordamiento de pila se debe a un código no administrado.|  
  
## <a name="remarks"></a>Comentarios  
 Esta información se pasa al host a través de una llamada al método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para hosts](hosting-enumerations.md)
