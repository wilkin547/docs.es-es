---
title: IHostCrst (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34a911668db09b255282833cec3e6272b315373b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618664"
---
# <a name="ihostcrst-interface"></a>IHostCrst (Interfaz)
Actúa como la representación del host de una sección crítica para el subprocesamiento.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Enter (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Entra en la sección crítica.|  
|[Leave (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Deja la sección crítica.|  
|[SetSpinCount (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Establece el recuento circular para la sección crítica.|  
|[TryEnter (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Intenta escribir una sección crítica y los informes correctamente o no inmediatamente.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostCrst` permite que common language runtime (CLR) para comunicarse directamente con la representación del host de una sección crítica, en lugar de usar las funciones de Win32 como `EnterCriticalSection` o `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
