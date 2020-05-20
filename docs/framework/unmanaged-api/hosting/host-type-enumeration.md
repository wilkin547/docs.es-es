---
title: HOST_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: e8dda83df8a320733f45dbcc13599cdf37d26492
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617157"
---
# <a name="host_type-enumeration"></a>HOST_TYPE (Enumeración)
Contiene valores que especifican el tipo de host que está iniciando una aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Inicie la aplicación desde AppLaunch. exe.<br /><br /> Use este valor para las aplicaciones de confianza parcial.|  
|`HOST_TYPE_CORFLAG`|Inicie la aplicación directamente. Es decir, inicie la aplicación desde su propio archivo. exe.<br /><br /> Use este valor para las aplicaciones de plena confianza.|  
|`HOST_TYPE_DEFAULT`|Igual que HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Enumeraciones para hosts](hosting-enumerations.md)
