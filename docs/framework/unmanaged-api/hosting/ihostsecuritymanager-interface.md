---
title: IHostSecurityManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b3d67328dbf68491d319e55e63a9c3540cd1ee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager (Interfaz)
Proporciona métodos que permiten el acceso y control sobre el contexto de seguridad del subproceso actualmente en ejecución.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetSecurityContext (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Obtiene el solicitado [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) desde el host.|  
|[ImpersonateLoggedOnUser (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Las solicitudes que se ejecuta código con las credenciales de identidad del usuario actual.|  
|[OpenThreadToken (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Se abre el símbolo (token) de acceso discrecional asociado al subproceso actual.|  
|[RevertToSelf (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Termina la suplantación de identidad del usuario actual y devuelve el token de subproceso original.|  
|[SetSecurityContext (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Establece el contexto de seguridad para el subproceso actualmente en ejecución.|  
|[SetThreadToken (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Establece un identificador para el subproceso actualmente en ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Un host puede controlar todo el acceso de código a los tokens de subprocesos por el common language runtime (CLR) y el código de usuario. También puede asegurar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código. `IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para CLR.  
  
 El CLR controla internamente el contexto de subproceso administrado. Consulta específico del proceso `IHostSecurityManager` en las situaciones siguientes:  
  
-   En el subproceso finalizador, durante la ejecución del finalizador.  
  
-   Durante la ejecución del constructor de clase y módulo.  
  
-   En los puntos asincrónicos en el subproceso de trabajo, en las llamadas a la [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) método.  
  
-   En servicio de los puertos de terminación de E/S.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IHostSecurityContext (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
