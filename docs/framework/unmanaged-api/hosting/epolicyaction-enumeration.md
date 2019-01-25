---
title: EPolicyAction (Enumeración)
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80a0e8d37e834ea0a7623517e2e1228a79d9ea10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655717"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction (Enumeración)
Describe las acciones de directiva, el host puede establecer para las operaciones descritas por [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
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
|`eAbortThread`|Especifica que common language runtime (CLR) debe anular correctamente el subproceso. Una anulación correcta incluye intentos de ejecutar todo `finally` bloquea cualquier `catch` bloques relacionados con las anulaciones de subproceso y los finalizadores.|  
|`eDisableRuntime`|Especifica que el CLR debe entrar en un estado deshabilitado. No se puede ejecutar código administrado en el proceso afectado y subprocesos se bloquean entre en CLR.|  
|`eExitProcess`|Especifica que el CLR debe intentar una salida correcta del proceso, incluidos los finalizadores en ejecución y realizar operaciones de limpieza y registro.|  
|`eFastExitProcess`|Especifica que el CLR debe salir del proceso inmediatamente, sin ejecutar los finalizadores ni realizar operaciones de limpieza y registro. Embargo, se envía la notificación al depurador.|  
|`eNoAction`|Especifica que no se debe tomar ninguna acción.|  
|`eRudeAbortThread`|Especifica que el CLR debe realizar una anulación a la fuerza. Solo los `catch` y `finally` los bloques marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.|  
|`eRudeExitProcess`|Especifica que el CLR debe salir del proceso sin ejecutar los finalizadores ni registrar las operaciones.|  
|`eRudeUnloadAppDomain`|Especifica que el CLR debe realizar una descarga forzada de la <xref:System.AppDomain>. Los finalizadores de sólo marcan con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan. De forma similar, todos los subprocesos con este <xref:System.AppDomain> en su pila recibir un `ThreadAbortException`, sino solamente aquello `catch` y `finally` los bloques marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.|  
|`eThrowException`|Especifica que debe iniciará una excepción correspondiente a la condición, por ejemplo, de memoria insuficiente, desbordamiento del búfer y así sucesivamente.|  
|`eUnloadAppDomain`|Especifica que el <xref:System.AppDomain> debe descargarse. El CLR intenta ejecutar los finalizadores.|  
  
## <a name="remarks"></a>Comentarios  
 El host establece las acciones de directiva mediante una llamada a métodos de la [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interfaz. Para obtener información sobre las anulaciones a la fuerza y estables, consulte el [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeración.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
