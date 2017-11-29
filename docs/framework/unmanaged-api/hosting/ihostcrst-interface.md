---
title: IHostCrst (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrst-interface"></a>IHostCrst (Interfaz)
Actúa como la representación del host de una sección crítica para el subprocesamiento.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Enter (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Entra en la sección crítica.|  
|[Leave (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Deja la sección crítica.|  
|[SetSpinCount (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Establece el recuento circular para la sección crítica.|  
|[TryEnter (método)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Intenta escribir la sección crítica y el éxito de informes o el error inmediatamente.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostCrst`permite que common language runtime (CLR) para comunicarse directamente con la representación del host de una sección crítica, en lugar de usar las funciones de Win32 como `EnterCriticalSection` o `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
