---
description: 'Más información sobre: enumeración StackOverflowType ('
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
ms.openlocfilehash: d39ccd99331a3e839236f1ede21254edb92b2dfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679373"
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`SO_ClrEngine`|El motor de ejecución produjo el desbordamiento de pila.|  
|`SO_Managed`|El desbordamiento de pila se produjo por código administrado.|  
|`SO_Other`|El desbordamiento de pila se debe a un código no administrado.|  
  
## <a name="remarks"></a>Observaciones  

 Esta información se pasa al host a través de una llamada al método [IActionOnCLREvent:: onEvent](iactiononclrevent-onevent-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](hosting-enumerations.md)
