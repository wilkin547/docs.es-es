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
ms.openlocfilehash: 1ae50fb3ff15097f9a6ca5839f3832bcfc58d3f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134852"
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits (Método)
Establece el tamaño del segmento y el tamaño máximo de la generación 0.  
  
> [!IMPORTANT]
> A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 en valores mayores que `DWORD` mediante el método [igchost2 (:: setgcstartuplimitsex (](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `SegmentSize`  
 de Tamaño del segmento utilizado por el sistema de recolección de elementos no utilizados.  
  
 `MaxGen0Size`  
 de Tamaño máximo de la generación 0.  
  
## <a name="remarks"></a>Comentarios  
 Solo se puede llamar una vez al método `SetGCStartupLimits`. Estos valores no se pueden cambiar más adelante.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
