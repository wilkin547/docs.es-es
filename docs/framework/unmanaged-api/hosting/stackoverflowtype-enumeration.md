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
ms.openlocfilehash: f09c6bb79d7bd28f4d8b74237b6f343a07b79062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141473"
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
 Esta información se pasa al host a través de una llamada al método [IActionOnCLREvent:: onEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
