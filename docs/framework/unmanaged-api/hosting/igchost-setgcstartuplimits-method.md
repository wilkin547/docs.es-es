---
title: "IGCHost::SetGCStartupLimits (Método)"
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
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d99212b1ece4d3c0ce9440ac973b8254ebca6dde
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits (Método)
Establece el tamaño del segmento y el tamaño máximo para la generación 0.  
  
> [!IMPORTANT]
>  A partir de la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], puede establecer un tamaño de segmento y mayor que los valores de tamaño máximo de generación 0 a `DWORD` mediante el uso de la [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `SegmentSize`  
 [in] El tamaño del segmento utilizado por el sistema de recopilación de elementos no utilizados.  
  
 `MaxGen0Size`  
 [in] El tamaño máximo para la generación 0.  
  
## <a name="remarks"></a>Comentarios  
 El `SetGCStartupLimits` sólo una vez puede llamar al método. Estos valores no se puede cambiar más adelante.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost.idl, GCHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IGCHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
