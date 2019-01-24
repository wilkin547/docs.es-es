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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a2db1aea04ae060623bc39a52ed6990f6137f82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606457"
---
# <a name="hosttype-enumeration"></a>HOST_TYPE (Enumeración)
Contiene valores que especifican el tipo de host que está iniciando una aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Iniciar la aplicación desde AppLaunch.exe.<br /><br /> Use este valor para las aplicaciones de confianza parcial.|  
|`HOST_TYPE_CORFLAG`|Inicie la aplicación directamente. Es decir, iniciar la aplicación desde su propio archivo .exe.<br /><br /> Use este valor para las aplicaciones de plena confianza.|  
|`HOST_TYPE_DEFAULT`|Igual que HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
