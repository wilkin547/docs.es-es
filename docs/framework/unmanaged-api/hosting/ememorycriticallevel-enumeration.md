---
title: EMemoryCriticalLevel (Enumeración)
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26b3761ab49f36c5f687ff2c62882667e044d299
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774218"
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel (Enumeración)
Contiene valores que indican el impacto de un error cuando se ha solicitado una asignación de memoria, pero no se puede satisfacer.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`eAppDomainCritical`|Indica que la asignación es esencial para ejecutar el código administrado en el dominio que ha solicitado la asignación. Si no se puede asignar memoria, el CLR no puede garantizar que el dominio está todavía se puede utilizar. El host decide qué acción realizar cuando no se puede satisfacer la asignación. Puede indicar a CLR para anular la `AppDomain` automáticamente, o permitir que siga ejecutándose llamando a métodos en [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Indica que la asignación es esencial para la ejecución de código administrado en el proceso. Este valor se utiliza durante el inicio y cuando se ejecuta los finalizadores. Si no se puede asignar memoria, el CLR no puede funcionar en el proceso. Si se produce un error en la asignación, se deshabilita el CLR. Se producirá un error en todas las llamadas subsiguientes a CLR HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Indica que la asignación es esencial para ejecutar la tarea que ha solicitado la asignación. Si no se puede asignar memoria, el CLR no puede garantizar que se puede ejecutar la tarea. En caso de error, el CLR genera un <xref:System.Threading.ThreadAbortException> en el subproceso de sistema de operación física.|  
  
## <a name="remarks"></a>Comentarios  
 Los métodos de asignación de memoria definidos en el [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) y [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces toman un parámetro de este tipo. Dependiendo de la gravedad de un error, un host puede decidir si un error en la solicitud de asignación inmediatamente o esperar hasta que se pueda satisfacer.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRMemoryNotificationCallback (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
