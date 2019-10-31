---
title: ICLROnEventManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: a1b22e77fe20d5e2d755efcd7a63c8f2bdc781e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140845"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager (Interfaz)
Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de Common Language Runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[RegisterActionOnEvent (método)](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|Registra un puntero de devolución de llamada para el evento especificado.|  
|[UnregisterActionOnEvent (método)](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Para registrar y anular el registro de las devoluciones de llamada de eventos, el host obtiene una referencia a `ICLROnEventManager` llamando al método [ICLRControl:: GetCLRManager (](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) .  
  
> [!NOTE]
> Los eventos descritos por [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrEvent (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [IActionOnCLREvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
