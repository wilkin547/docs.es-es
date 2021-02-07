---
description: 'Más información sobre: IGCHost:: Setgcstartuplimits ((método)'
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
ms.openlocfilehash: 91c74d54189bbfb7e9f208e507fe6e75b7023e00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709508"
---
# <a name="igchostsetgcstartuplimits-method"></a>IGCHost::SetGCStartupLimits (Método)

Establece el tamaño del segmento y el tamaño máximo de la generación 0.  
  
> [!IMPORTANT]
> A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 en valores mayores que mediante `DWORD` el método [igchost2 (:: setgcstartuplimitsex (](igchost2-setgcstartuplimitsex-method.md) .  
  
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
  
## <a name="remarks"></a>Observaciones  

 `SetGCStartupLimits`Solo se puede llamar una vez al método. Estos valores no se pueden cambiar más adelante.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCHost (Interfaz)](igchost-interface.md)
