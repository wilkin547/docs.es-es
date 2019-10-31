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
ms.openlocfilehash: 993d16818b25dfefe1f53c7afd06bc9857d9eb24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121522"
---
# <a name="ihostsecuritycontext-interface"></a>IHostSecurityContext (Interfaz)
Permite que el Common Language Runtime (CLR) Mantenga la información de contexto de seguridad implementada por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Capture (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|Obtiene un clon de la instancia de `IHostSecurityContext` devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Comentarios  
 Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el código de usuario y el CLR. También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código. `IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución. El motor en tiempo de ejecución captura esta información mediante `Capture`y la mueve entre el envío de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y los constructores de clase y módulo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRHostProtectionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [IHostSecurityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
