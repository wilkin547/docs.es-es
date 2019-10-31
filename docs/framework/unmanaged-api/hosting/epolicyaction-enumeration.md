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
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138232"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction (Enumeración)
Describe las acciones de directiva que el host puede establecer para las operaciones descritas por [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por [eclrfailure (](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`eAbortThread`|Especifica que el Common Language Runtime (CLR) debe anular correctamente el subproceso. Una anulación correcta incluye intentos de ejecutar todos los bloques de `finally`, los bloques de `catch` relacionados con las anulaciones de subprocesos y los finalizadores.|  
|`eDisableRuntime`|Especifica que CLR debe entrar en un Estado deshabilitado. No se puede ejecutar más código administrado en el proceso afectado y se impide que los subprocesos entren en el CLR.|  
|`eExitProcess`|Especifica que CLR debe intentar una salida correcta del proceso, incluidos los finalizadores en ejecución y la realización de operaciones de limpieza y registro.|  
|`eFastExitProcess`|Especifica que CLR debe salir del proceso inmediatamente, sin ejecutar finalizadores ni realizar operaciones de limpieza y registro. Sin embargo, se envía una notificación al depurador.|  
|`eNoAction`|Especifica que no se debe realizar ninguna acción.|  
|`eRudeAbortThread`|Especifica que CLR debe realizar una anulación de subproceso forzada. Solo se ejecutan los bloques `catch` y `finally` marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.|  
|`eRudeExitProcess`|Especifica que CLR debe salir del proceso sin ejecutar finalizadores ni operaciones de registro.|  
|`eRudeUnloadAppDomain`|Especifica que CLR debe realizar una descarga forzada del <xref:System.AppDomain>. Solo se ejecutan los finalizadores marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>. De forma similar, todos los subprocesos con este <xref:System.AppDomain> en su pila reciben un `ThreadAbortException`, pero solo se ejecutan los bloques `catch` y `finally` marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.|  
|`eThrowException`|Especifica que debe producirse una excepción adecuada a la condición, como memoria insuficiente, desbordamiento del búfer, etc.|  
|`eUnloadAppDomain`|Especifica que se debe descargar el <xref:System.AppDomain>. CLR intenta ejecutar los finalizadores.|  
  
## <a name="remarks"></a>Comentarios  
 El host establece las acciones de Directiva mediante una llamada a los métodos de la interfaz [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) . Para obtener información sobre las anulaciones superficiales y correctas, vea la enumeración [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrFailure (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
