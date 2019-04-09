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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7486a094deab16ebbc05f19f1b652126479ce11c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183006"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager (Interfaz)
Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de common language runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|Registra un puntero de devolución de llamada para el evento especificado.|  
|[Método UnregisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|Anula el registro de un puntero de devolución de llamada registrada anteriormente para el evento especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Para registrar y anular el registro de las devoluciones de llamada de evento, el host obtiene una referencia a `ICLROnEventManager` mediante una llamada a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método.  
  
> [!NOTE]
>  Los eventos descritos por [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) pueden activar más de una vez y desde diferentes subprocesos para indicar una descarga o la deshabilitación de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrEvent (Enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [IActionOnCLREvent (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
