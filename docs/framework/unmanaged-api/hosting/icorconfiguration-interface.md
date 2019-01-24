---
title: ICorConfiguration (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7abd6b4ca97173cfecbabf1a8b90afcf3c48a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554184"
---
# <a name="icorconfiguration-interface"></a>ICorConfiguration (Interfaz)
Proporciona métodos para la configuración de common language runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AddDebuggerSpecialThread (método)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|Indica a los servicios de depuración que un subproceso en particular debe permitirse seguirse ejecutando mientras el depurador tiene una aplicación detenida en escenarios de depuración administrados o no administrado.|  
|[SetDebuggerThreadControl (método)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|Establece la interfaz de devolución de llamada que se llamará los servicios de depuración como subprocesos CLR se bloquea y desbloquea para la depuración.|  
|[SetGCHostControl (método)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|Establece la interfaz de devolución de llamada que se usará por el recolector de elementos no utilizados para solicitar al host que cambie los límites de memoria virtual.|  
|[SetGCThreadControl (método)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|Establece la interfaz de devolución de llamada para la programación de subprocesos para tareas que no son de tiempo de ejecución que de lo contrario, se bloquearía para una colección de elementos no utilizados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost (coclase)](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
