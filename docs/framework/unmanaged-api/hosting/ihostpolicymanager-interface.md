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
ms.openlocfilehash: d6b34403a45cc40863d79b59396041e496989045
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503944"
---
# <a name="ihostpolicymanager-interface"></a>IHostPolicyManager (Interfaz)
Proporciona métodos que envían una notificación al host de las acciones que realiza el Common Language Runtime (CLR) en caso de anulaciones, tiempos de espera o errores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método OnDefaultAction](ihostpolicymanager-ondefaultaction-method.md)|Notifica al host que CLR está a punto de realizar la acción predeterminada especificada por una llamada a [ICLRPolicyManager:: SetDefaultAction (](iclrpolicymanager-setdefaultaction-method.md) en respuesta a una anulación o descarga del subproceso <xref:System.AppDomain> .|  
|[Método OnFailure](ihostpolicymanager-onfailure-method.md)|Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: setactiononfailure (](iclrpolicymanager-setactiononfailure-method.md) en respuesta a un error de asignación de recursos o de recorte.|  
|[Método OnTimeout](ihostpolicymanager-ontimeout-method.md)|Notifica al host que el CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnTimeout (](iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [EClrFailure (Enumeración)](eclrfailure-enumeration.md)
- [EClrOperation (Enumeración)](eclroperation-enumeration.md)
- [EPolicyAction (Enumeración)](epolicyaction-enumeration.md)
- [ICLRPolicyManager (Interfaz)](iclrpolicymanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
