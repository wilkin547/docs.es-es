---
title: "HOST_TYPE (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: HOST_TYPE
api_location: mscoree.dll
api_type: COM
f1_keywords: HOST_TYPE
helpviewer_keywords: HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e191293ff7bde6b1be2210af4e7830fec0d7290d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
|`HOST_TYPE_APPLAUNCH`|Inicie la aplicación desde AppLaunch.exe.<br /><br /> Use este valor para aplicaciones de confianza parcial.|  
|`HOST_TYPE_CORFLAG`|Inicie la aplicación directamente. Es decir, inicie la aplicación desde su propio archivo .exe.<br /><br /> Use este valor para las aplicaciones de plena confianza.|  
|`HOST_TYPE_DEFAULT`|Igual que HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
