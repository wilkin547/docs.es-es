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
ms.openlocfilehash: 7d935bff023d806cf8cfb6d87bde0f82666b51b5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131122"
---
# <a name="eclrfailure-enumeration"></a>EClrFailure (Enumeración)
Describe el conjunto de errores para los que un host puede establecer acciones de directiva.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`FAIL_NonCriticalResource`|Se produjo un error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región de código que no es crítica.|  
|`FAIL_CriticalResource`|Se produjo un error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región crítica de código.|  
|`FAIL_FatalRuntime`|El Common Language Runtime (CLR) ya no puede ejecutar código administrado en el proceso. En adelante, las llamadas a las funciones de hospedaje devuelven un valor HRESULT de HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Un subproceso no pudo liberar un bloqueo al devolver un objeto <xref:System.AppDomain>. El host no puede establecer este error para hacer que un subproceso se anule.|  
|`FAIL_StackOverflow`|Se ha producido un desbordamiento de pila.|  
|`FAIL_AccessViolation`|Se intentó leer o escribir en la memoria protegida. No se admite en el .NET Framework 4.|  
|`FAIL_CodeContract`|Error de contrato de código. Vea [contratos de código](../../../../docs/framework/debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Comentarios  
 Vea el método [ICLRPolicyManager:: setactiononfailure (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) para obtener una lista de los valores de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) que el host puede usar para especificar las acciones de directiva para las condiciones de error. Para obtener más información sobre las regiones críticas y no críticas de código, vea [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [SetActionOnFailure (método)](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)
- [IHostPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
