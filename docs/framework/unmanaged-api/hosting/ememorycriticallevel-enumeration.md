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
ms.openlocfilehash: acf4f3f582e417c5e7b814622986427f996796ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel (Enumeración)
Contiene valores que indican el impacto de un error cuando se ha solicitado una asignación de memoria concreta, pero no se puede satisfacer.  
  
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
|`eAppDomainCritical`|Indica que la asignación es esencial para la ejecución de código administrado en el dominio que ha solicitado la asignación. Si no se puede asignar memoria, el CLR no puede garantizar que el dominio es podría utilizar. El host decide qué acción realizar cuando no se puede satisfacer la asignación. Puede indicar a CLR que se debe anular la `AppDomain` automáticamente, o permitir que siga ejecutándose llamando a métodos en [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Indica que la asignación es esencial para la ejecución de código administrado en el proceso. Este valor se utiliza durante el inicio y cuando los finalizadores en ejecución. Si no se puede asignar memoria, el CLR no puede funcionar en el proceso. Si se produce un error en la asignación, se deshabilita el CLR. Todas las llamadas subsiguientes a CLR producen el error HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Indica que la asignación es esencial para ejecutar la tarea que ha solicitado la asignación. Si no se puede asignar memoria, el CLR no puede garantizar que se puede ejecutar la tarea. En caso de error, el CLR genera un <xref:System.Threading.ThreadAbortException> en el subproceso del sistema operativo físico.|  
  
## <a name="remarks"></a>Comentarios  
 Los métodos de asignación de memoria definidos en el [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) y [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces toman un parámetro de este tipo. Dependiendo de la gravedad del error, un host puede decidir si se producirá un error en la solicitud de asignación inmediatamente o esperar hasta que se pueda satisfacer.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRMemoryNotificationCallback (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
