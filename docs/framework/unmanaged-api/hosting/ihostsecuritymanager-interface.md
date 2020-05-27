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
ms.openlocfilehash: b2c334c7a757c2f4044d08787bdae93ffc2804e4
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803895"
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager (Interfaz)
Proporciona métodos que permiten el acceso y el control sobre el contexto de seguridad del subproceso que se está ejecutando actualmente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Obtiene el [IHostSecurityContext](ihostsecuritycontext-interface.md) solicitado del host.|  
|[Método ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md)|Solicita que el código se ejecute con las credenciales de la identidad del usuario actual.|  
|[Método OpenThreadToken](ihostsecuritymanager-openthreadtoken-method.md)|Abre el token de acceso discrecional asociado al subproceso actual.|  
|[Método RevertToSelf](ihostsecuritymanager-reverttoself-method.md)|Finaliza la suplantación de la identidad del usuario actual y devuelve el token del subproceso original.|  
|[Método SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md)|Establece el contexto de seguridad para el subproceso que se está ejecutando actualmente.|  
|[Método SetThreadToken](ihostsecuritymanager-setthreadtoken-method.md)|Establece un identificador para el subproceso que se está ejecutando actualmente.|  
  
## <a name="remarks"></a>Observaciones  
 Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el Common Language Runtime (CLR) y el código de usuario. También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código. `IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para CLR.  
  
 CLR controla internamente el contexto del subproceso administrado. Consulta el específico del proceso `IHostSecurityManager` en las situaciones siguientes:  
  
- En el subproceso finalizador, durante la ejecución del finalizador.  
  
- Durante la ejecución del constructor de la clase y del módulo.  
  
- En los puntos asincrónicos del subproceso de trabajo, en llamadas al método [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) .  
  
- En el servicio de puertos de finalización de e/s.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostSecurityContext (Interfaz)](ihostsecuritycontext-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
