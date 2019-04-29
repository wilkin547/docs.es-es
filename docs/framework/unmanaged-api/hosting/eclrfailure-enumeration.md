---
title: EClrFailure (Enumeración)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19dacae05766566521f563d0d24980c01dfb7a0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796155"
---
# <a name="eclrfailure-enumeration"></a>EClrFailure (Enumeración)
Describe el conjunto de errores para el que un host puede establecer acciones de directiva.  
  
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
|`FAIL_NonCriticalResource`|Error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región no crítica del código.|  
|`FAIL_CriticalResource`|Error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región crítica del código.|  
|`FAIL_FatalRuntime`|Common language runtime (CLR) ya no es capaz de ejecutar código administrado en el proceso. Aquí en adelante, las llamadas a las funciones de hospedaje devuelven un valor HRESULT de HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Un subproceso no pudo liberar un bloqueo al volver de un <xref:System.AppDomain> objeto. El host no puede establecer este error para hacer que un subproceso se anule.|  
|`FAIL_StackOverflow`|Se ha producido un desbordamiento de pila.|  
|`FAIL_AccessViolation`|Se intentó leer o escribir en la memoria protegida. No se admite en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].|  
|`FAIL_CodeContract`|Se ha producido un error de contrato de código. Consulte [contratos de código](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Comentarios  
 Consulte la [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) método para obtener una lista de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores el host puede utilizar para especificar las acciones de directiva para las condiciones de error. Para obtener más información acerca de las regiones que no son críticas y de código, vea [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [SetActionOnFailure (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
