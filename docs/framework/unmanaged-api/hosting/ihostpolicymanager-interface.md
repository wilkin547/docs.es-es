---
title: IHostPolicyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: 6ba7b7adc104db528293d77c3591370c6ce02c25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128599"
---
# <a name="ihostpolicymanager-interface"></a>IHostPolicyManager (Interfaz)
Proporciona métodos que envían una notificación al host de las acciones que realiza el Common Language Runtime (CLR) en caso de anulaciones, tiempos de espera o errores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[OnDefaultAction (método)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|Notifica al host que CLR está a punto de realizar la acción predeterminada especificada por una llamada a [ICLRPolicyManager:: SetDefaultAction (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) en respuesta a una anulación del subproceso o <xref:System.AppDomain> descarga.|  
|[OnFailure (método)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: setactiononfailure (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) en respuesta a un error de asignación de recursos o de recorte.|  
|[OnTimeout (método)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|Notifica al host que el CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnTimeout (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EClrOperation (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction (enumeración)](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
