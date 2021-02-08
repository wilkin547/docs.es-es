---
description: 'Más información acerca de: enumeración de EPolicyAction'
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
ms.openlocfilehash: fb66de2211972bd4d25ccfbab4965f315c0144a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785476"
---
# <a name="epolicyaction-enumeration"></a>EPolicyAction (Enumeración)

Describe las acciones de directiva que el host puede establecer para las operaciones descritas por [EClrOperation](eclroperation-enumeration.md) y los errores descritos por [eclrfailure (](eclrfailure-enumeration.md).  
  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eAbortThread`|Especifica que el Common Language Runtime (CLR) debe anular correctamente el subproceso. Una anulación correcta incluye los intentos de ejecutar todos los `finally` bloques, los `catch` bloques relacionados con las anulaciones de subprocesos y los finalizadores.|  
|`eDisableRuntime`|Especifica que CLR debe entrar en un Estado deshabilitado. No se puede ejecutar más código administrado en el proceso afectado y se impide que los subprocesos entren en el CLR.|  
|`eExitProcess`|Especifica que CLR debe intentar una salida correcta del proceso, incluidos los finalizadores en ejecución y la realización de operaciones de limpieza y registro.|  
|`eFastExitProcess`|Especifica que CLR debe salir del proceso inmediatamente, sin ejecutar finalizadores ni realizar operaciones de limpieza y registro. Sin embargo, se envía una notificación al depurador.|  
|`eNoAction`|Especifica que no se debe realizar ninguna acción.|  
|`eRudeAbortThread`|Especifica que CLR debe realizar una anulación de subproceso forzada. Solo `catch` `finally` se ejecutan los bloques y marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .|  
|`eRudeExitProcess`|Especifica que CLR debe salir del proceso sin ejecutar finalizadores ni operaciones de registro.|  
|`eRudeUnloadAppDomain`|Especifica que CLR debe realizar una descarga forzada de <xref:System.AppDomain> . Solo se ejecutan los finalizadores marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> . De forma similar, todos los subprocesos con este <xref:System.AppDomain> en su pila reciben `ThreadAbortException` , pero solo `catch` `finally` <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan los bloques y marcados con.|  
|`eThrowException`|Especifica que debe producirse una excepción adecuada a la condición, como memoria insuficiente, desbordamiento del búfer, etc.|  
|`eUnloadAppDomain`|Especifica que <xref:System.AppDomain> se debe descargar. CLR intenta ejecutar los finalizadores.|  
  
## <a name="remarks"></a>Observaciones  

 El host establece las acciones de Directiva mediante una llamada a los métodos de la interfaz [ICLRPolicyManager](iclrpolicymanager-interface.md) . Para obtener información sobre las anulaciones superficiales y correctas, vea la enumeración [EClrOperation](eclroperation-enumeration.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrFailure (Enumeración)](eclrfailure-enumeration.md)
- [ICLRPolicyManager (Interfaz)](iclrpolicymanager-interface.md)
- [IHostPolicyManager (Interfaz)](ihostpolicymanager-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
