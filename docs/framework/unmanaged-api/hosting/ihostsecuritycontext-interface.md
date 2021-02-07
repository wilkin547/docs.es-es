---
description: 'Más información sobre: IHostSecurityContext (interfaz)'
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
ms.openlocfilehash: c4c1be00a8b1c9df58797a0f2fc7e60abcab9673
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671651"
---
# <a name="ihostsecuritycontext-interface"></a>IHostSecurityContext (Interfaz)

Permite que el Common Language Runtime (CLR) Mantenga la información de contexto de seguridad implementada por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Capture](ihostsecuritycontext-capture-method.md)|Obtiene un clon de la `IHostSecurityContext` instancia de devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Observaciones  

 Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el código de usuario y el CLR. También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código. `IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución. El motor en tiempo de ejecución captura esta información mediante `Capture` y la mueve entre la distribución de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y los constructores de clase y módulo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRHostProtectionManager (Interfaz)](iclrhostprotectionmanager-interface.md)
- [IHostSecurityManager (Interfaz)](ihostsecuritymanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
