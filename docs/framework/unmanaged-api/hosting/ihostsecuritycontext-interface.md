---
title: IHostSecurityContext (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d71b7e1265110a70329377ce8ab7430e1943c49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984300"
---
# <a name="ihostsecuritycontext-interface"></a>IHostSecurityContext (Interfaz)
Permite que common language runtime (CLR) para conservar la información de contexto de seguridad implementado por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Capture (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|Obtiene un clon de la `IHostSecurityContext` devuelve la instancia de una llamada a [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Comentarios  
 Un host puede controlar todo el acceso de código a los tokens de subprocesos por código de usuario y el CLR. También puede garantizar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código. `IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución. El tiempo de ejecución captura esta información mediante `Capture`, y se mueve a través del envío de elemento de trabajo de grupo de subprocesos, la ejecución del finalizador y los constructores de módulo y clase.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRHostProtectionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [IHostSecurityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
