---
title: IGCHost::SetGCStartupLimits (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 365261883f0b81884bb7cf70614628c05f9067c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993270"
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits (Método)
Establece el tamaño del segmento y el tamaño máximo para la generación 0.  
  
> [!IMPORTANT]
>  A partir de la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], puede establecer el tamaño de segmento y mayor que los valores de tamaño máximo de generación 0 a `DWORD` utilizando el [Igchost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `SegmentSize`  
 [in] El tamaño del segmento utilizado por el sistema de recopilación de elementos no utilizados.  
  
 `MaxGen0Size`  
 [in] El tamaño máximo para la generación 0.  
  
## <a name="remarks"></a>Comentarios  
 El `SetGCStartupLimits` puede llamar al método una sola vez. No se puede cambiar estos valores más adelante.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: GCHost.idl, GCHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
