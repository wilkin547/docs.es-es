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
ms.openlocfilehash: 4ee8705d00e1f63f69863d0bf8e7d0d9d62807e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122296"
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel (Enumeración)
Contiene valores que indican el impacto de un error cuando se ha solicitado una asignación de memoria, pero no se puede satisfacer.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
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
