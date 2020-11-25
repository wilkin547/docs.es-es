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
ms.openlocfilehash: 3b9ad4b40ce94420f2ab5fc25335c41dec15dc09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720560"
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel (Enumeración)

Contiene valores que indican el impacto de un error cuando se ha solicitado una determinada asignación de memoria, pero no se puede satisfacer.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eAppDomainCritical`|Indica que la asignación es fundamental para ejecutar el código administrado en el dominio que ha solicitado la asignación. Si no se puede asignar memoria, CLR no puede garantizar que el dominio siga siendo utilizable. El host decide qué acción debe realizarse cuando no se puede satisfacer la asignación. Puede indicar a CLR que anule `AppDomain` automáticamente o que permita que se siga ejecutando llamando a los métodos en [ICLRPolicyManager](iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Indica que la asignación es fundamental para la ejecución de código administrado en el proceso. Este valor se utiliza durante el inicio y al ejecutar los finalizadores. Si no se puede asignar memoria, CLR no puede funcionar en el proceso. Si se produce un error en la asignación, el CLR se deshabilita en efecto. Se producirá un error en todas las llamadas subsiguientes a CLR con HOST_E_CLRNOTAVAILABLE.|  
|`eTaskCritical`|Indica que la asignación es fundamental para ejecutar la tarea que ha solicitado la asignación. Si no se puede asignar memoria, CLR no puede garantizar que la tarea se pueda ejecutar. En caso de error, CLR genera una <xref:System.Threading.ThreadAbortException> en el subproceso del sistema operativo físico.|  
  
## <a name="remarks"></a>Comentarios  

 Los métodos de asignación de memoria definidos en las interfaces [IHostMemoryManager](ihostmemorymanager-interface.md) y [IHostMAlloc](ihostmalloc-interface.md) toman un parámetro de este tipo. Dependiendo de la gravedad de un error, un host puede decidir si se producirá un error de la solicitud de asignación inmediatamente o se esperará hasta que se pueda satisfacer.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRMemoryNotificationCallback (Interfaz)](iclrmemorynotificationcallback-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
