---
title: "EPolicyAction (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5de55d46eead37962fad7d7c1c5bd1766e772fe8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction (Enumeración)
Describe las acciones de directiva que el host puede establecer para las operaciones descritas por [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eAbortThread`|Especifica que common language runtime (CLR) debe anular correctamente el subproceso. Una anulación correcta incluye intentar ejecutar todos los `finally` bloquea cualquier `catch` bloques relacionados con anulaciones de subprocesos y los finalizadores.|  
|`eDisableRuntime`|Especifica que el CLR debe entrar en un estado deshabilitado. Ninguna otra se puede ejecutar código administrado en el proceso afectado, y subprocesos bloqueados entren en el CLR.|  
|`eExitProcess`|Especifica que el CLR debe intentar una salida correcta del proceso, incluidos los finalizadores en ejecución y realizar operaciones de limpieza y el registro.|  
|`eFastExitProcess`|Especifica que el CLR debe salir del proceso de inmediato, sin ejecutar los finalizadores ni realizar operaciones de limpieza y el registro. Embargo, la notificación se envía al depurador.|  
|`eNoAction`|Especifica que no llevará a cabo ninguna acción.|  
|`eRudeAbortThread`|Especifica que el CLR debe realizar una anulación de subproceso forzada. Solo los `catch` y `finally` los bloques marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.|  
|`eRudeExitProcess`|Especifica que el CLR debe salir del proceso sin ejecutar los finalizadores ni las operaciones de registro.|  
|`eRudeUnloadAppDomain`|Especifica que el CLR debe realizar una descarga forzada de la <xref:System.AppDomain>. Solo los finalizadores marcan con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan. De forma similar, todos los subprocesos con este <xref:System.AppDomain> en su pila reciben un `ThreadAbortException`, sino únicamente aquellas `catch` y `finally` los bloques marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.|  
|`eThrowException`|Especifica que se debe producir una excepción apropiada a la condición, como memoria insuficiente, desbordamiento de búfer y así sucesivamente.|  
|`eUnloadAppDomain`|Especifica que el <xref:System.AppDomain> debe descargarse. El CLR intenta ejecutar los finalizadores.|  
  
## <a name="remarks"></a>Comentarios  
 El host establece las acciones de la directiva mediante una llamada a métodos de la [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interfaz. Para obtener información sobre las anulaciones forzadas y correctas, vea la [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
