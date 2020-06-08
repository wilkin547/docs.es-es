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
ms.openlocfilehash: f6e25bfe11880730f6f447ccc0406d716d185624
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501500"
---
# <a name="ihostsecuritycontext-interface"></a>IHostSecurityContext (Interfaz)
Permite que el Common Language Runtime (CLR) Mantenga la información de contexto de seguridad implementada por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Capture](ihostsecuritycontext-capture-method.md)|Obtiene un clon de la `IHostSecurityContext` instancia de devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).|  
  
## <a name="remarks"></a>Comentarios  
 Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el código de usuario y el CLR. También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código. `IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución. El motor en tiempo de ejecución captura esta información mediante `Capture` y la mueve entre la distribución de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y los constructores de clase y módulo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRHostProtectionManager (Interfaz)](iclrhostprotectionmanager-interface.md)
- [IHostSecurityManager (Interfaz)](ihostsecuritymanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
