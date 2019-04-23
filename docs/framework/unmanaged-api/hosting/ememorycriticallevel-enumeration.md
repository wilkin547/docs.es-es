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
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="4f75e-102">EMemoryCriticalLevel (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4f75e-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="4f75e-103">Contiene valores que indican el impacto de un error cuando se ha solicitado una asignación de memoria, pero no se puede satisfacer.</span><span class="sxs-lookup"><span data-stu-id="4f75e-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f75e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f75e-104">Syntax</span></span>  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="4f75e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4f75e-105">Members</span></span>  
  
|<span data-ttu-id="4f75e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4f75e-106">Member</span></span>|<span data-ttu-id="4f75e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f75e-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="4f75e-108">Indica que la asignación es esencial para ejecutar el código administrado en el dominio que ha solicitado la asignación.</span><span class="sxs-lookup"><span data-stu-id="4f75e-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="4f75e-109">Si no se puede asignar memoria, el CLR no puede garantizar que el dominio está todavía se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="4f75e-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="4f75e-110">El host decide qué acción realizar cuando no se puede satisfacer la asignación.</span><span class="sxs-lookup"><span data-stu-id="4f75e-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="4f75e-111">Puede indicar a CLR para anular la `AppDomain` automáticamente, o permitir que siga ejecutándose llamando a métodos en [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4f75e-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="4f75e-112">Indica que la asignación es esencial para la ejecución de código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4f75e-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="4f75e-113">Este valor se utiliza durante el inicio y cuando se ejecuta los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="4f75e-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="4f75e-114">Si no se puede asignar memoria, el CLR no puede funcionar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4f75e-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="4f75e-115">Si se produce un error en la asignación, se deshabilita el CLR.</span><span class="sxs-lookup"><span data-stu-id="4f75e-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="4f75e-116">Se producirá un error en todas las llamadas subsiguientes a CLR HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4f75e-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="4f75e-117">Indica que la asignación es esencial para ejecutar la tarea que ha solicitado la asignación.</span><span class="sxs-lookup"><span data-stu-id="4f75e-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="4f75e-118">Si no se puede asignar memoria, el CLR no puede garantizar que se puede ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="4f75e-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="4f75e-119">En caso de error, el CLR genera un <xref:System.Threading.ThreadAbortException> en el subproceso de sistema de operación física.</span><span class="sxs-lookup"><span data-stu-id="4f75e-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f75e-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f75e-120">Remarks</span></span>  
 <span data-ttu-id="4f75e-121">Los métodos de asignación de memoria definidos en el [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) y [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces toman un parámetro de este tipo.</span><span class="sxs-lookup"><span data-stu-id="4f75e-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="4f75e-122">Dependiendo de la gravedad de un error, un host puede decidir si un error en la solicitud de asignación inmediatamente o esperar hasta que se pueda satisfacer.</span><span class="sxs-lookup"><span data-stu-id="4f75e-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f75e-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f75e-123">Requirements</span></span>  
 <span data-ttu-id="4f75e-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f75e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f75e-125">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f75e-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f75e-126">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f75e-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f75e-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f75e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f75e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f75e-128">See also</span></span>

- [<span data-ttu-id="4f75e-129">ICLRMemoryNotificationCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f75e-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="4f75e-130">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="4f75e-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
