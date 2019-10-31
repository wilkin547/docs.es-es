---
title: IHostSecurityManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 9b7cc41848e41976f388e38bf22c9ea0f90abbae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121477"
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager (Interfaz)
Proporciona métodos que permiten el acceso y el control sobre el contexto de seguridad del subproceso que se está ejecutando actualmente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetSecurityContext (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Obtiene el [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) solicitado del host.|  
|[ImpersonateLoggedOnUser (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Solicita que el código se ejecute con las credenciales de la identidad del usuario actual.|  
|[OpenThreadToken (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Abre el token de acceso discrecional asociado al subproceso actual.|  
|[RevertToSelf (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Finaliza la suplantación de la identidad del usuario actual y devuelve el token del subproceso original.|  
|[SetSecurityContext (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Establece el contexto de seguridad para el subproceso que se está ejecutando actualmente.|  
|[SetThreadToken (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Establece un identificador para el subproceso que se está ejecutando actualmente.|  
  
## <a name="remarks"></a>Comentarios  
 Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el Common Language Runtime (CLR) y el código de usuario. También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código. `IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para CLR.  
  
 CLR controla internamente el contexto del subproceso administrado. Consulta el `IHostSecurityManager` específico del proceso en las situaciones siguientes:  
  
- En el subproceso finalizador, durante la ejecución del finalizador.  
  
- Durante la ejecución del constructor de la clase y del módulo.  
  
- En los puntos asincrónicos del subproceso de trabajo, en llamadas al método [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) .  
  
- En el servicio de puertos de finalización de e/s.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostSecurityContext (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
