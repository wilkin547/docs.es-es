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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f45379fe8640ef7e7b3917bac8d10ca956d75ffb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957591"
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager (Interfaz)
Proporciona métodos que permiten el acceso y control sobre el contexto de seguridad del subproceso en ejecución actualmente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetSecurityContext (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Obtiene el solicitado [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) desde el host.|  
|[ImpersonateLoggedOnUser (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Las solicitudes que se ejecuta código mediante las credenciales de la identidad del usuario actual.|  
|[OpenThreadToken (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Se abre el token de acceso discrecional asociado al subproceso actual.|  
|[RevertToSelf (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Termina la suplantación de identidad del usuario actual y devuelve el token de subproceso original.|  
|[SetSecurityContext (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Establece el contexto de seguridad para el subproceso actualmente en ejecución.|  
|[SetThreadToken (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Establece un identificador para el subproceso actualmente en ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Un host puede controlar todo el acceso de código a los tokens de subprocesos por el common language runtime (CLR) y el código de usuario. También puede garantizar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código. `IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para el CLR.  
  
 CLR controla internamente el contexto de subproceso administrado. Consulta específico del proceso `IHostSecurityManager` en las situaciones siguientes:  
  
- En el subproceso de finalizador, durante la ejecución del finalizador.  
  
- Durante la ejecución del constructor de clase y el módulo.  
  
- En los puntos asincrónicos en el subproceso de trabajo, en las llamadas a la [IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) método.  
  
- En el mantenimiento de los puertos de finalización de E/S.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostSecurityContext (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
