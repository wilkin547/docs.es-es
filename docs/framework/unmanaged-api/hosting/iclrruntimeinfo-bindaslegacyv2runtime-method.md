---
title: "ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5552214f722cd7f9a56c2fce1e7c67de41d5bb1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>ICLRRuntimeInfo::BindAsLegacyV2Runtime (Método)
Enlaza el runtime actual para todos los heredados common language runtime (CLR) versión 2 activación decisiones sobre la directiva.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT concretos:  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El enlace se realizó correctamente o este runtime ya estaba enlazado como el runtime de la directiva de activación 2 de versión CLR heredado.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Un runtime diferente ya se enlazó a la directiva de activación 2 de versión CLR heredada.|  
  
## <a name="remarks"></a>Comentarios  
 Si el tiempo de ejecución actual ya está enlazado para todos los heredados CLR versión 2 activación decisiones sobre la directiva (por ejemplo, mediante la `useLegacyV2RuntimeActivationPolicy` del atributo en el [ \<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) en el archivo de configuración), este método no devuelve un resultado de error; en su lugar, el resultado es S_OK, igual que sería si el método tenía enlazar correctamente la directiva de activación heredada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRRuntimeInfo (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [\<Inicio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
