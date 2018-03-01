---
title: "EClrFailure (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e25a5378349dd476321765bb085db958e29670e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="eclrfailure-enumeration"></a>EClrFailure (Enumeración)
Describe el conjunto de errores para los que un host puede establecer acciones de la directiva.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Se produjo un error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región no crítica del código.|  
|`FAIL_CriticalResource`|Se produjo un error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región crítica del código.|  
|`FAIL_FatalRuntime`|Common language runtime (CLR) ya no es capaz de ejecutar código administrado en el proceso. Ahora en adelante, las llamadas a funciones de hospedaje devuelven un valor HRESULT de HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Un subproceso no pudo liberar un bloqueo al volver de un <xref:System.AppDomain> objeto. El host no puede establecer este error para hacer que un subproceso anular la operación.|  
|`FAIL_StackOverflow`|Se ha producido un desbordamiento de pila.|  
|`FAIL_AccessViolation`|Se intentó leer o escribir en la memoria protegida. No se admite en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].|  
|`FAIL_CodeContract`|Se produjo un error de contrato de código. Vea [contratos de código](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Comentarios  
 Consulte la [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) método para obtener una lista de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores que el host puede utilizar para especificar las acciones de directiva para condiciones de error. Para obtener más información acerca de las regiones críticas y no críticas de código, vea [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [SetActionOnFailure (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
