---
description: 'Más información sobre: enumeración Ememorycriticallevel ('
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
ms.openlocfilehash: 88965a29164de1ec7b01c2fcc8f51415127e69fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785437"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="8642a-103">EMemoryCriticalLevel (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8642a-103">EMemoryCriticalLevel Enumeration</span></span>

<span data-ttu-id="8642a-104">Contiene valores que indican el impacto de un error cuando se ha solicitado una determinada asignación de memoria, pero no se puede satisfacer.</span><span class="sxs-lookup"><span data-stu-id="8642a-104">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8642a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8642a-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="8642a-106">Members</span><span class="sxs-lookup"><span data-stu-id="8642a-106">Members</span></span>  
  
|<span data-ttu-id="8642a-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="8642a-107">Member</span></span>|<span data-ttu-id="8642a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8642a-108">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="8642a-109">Indica que la asignación es fundamental para ejecutar el código administrado en el dominio que ha solicitado la asignación.</span><span class="sxs-lookup"><span data-stu-id="8642a-109">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="8642a-110">Si no se puede asignar memoria, CLR no puede garantizar que el dominio siga siendo utilizable.</span><span class="sxs-lookup"><span data-stu-id="8642a-110">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="8642a-111">El host decide qué acción debe realizarse cuando no se puede satisfacer la asignación.</span><span class="sxs-lookup"><span data-stu-id="8642a-111">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="8642a-112">Puede indicar a CLR que anule `AppDomain` automáticamente o que permita que se siga ejecutando llamando a los métodos en [ICLRPolicyManager](iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8642a-112">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="8642a-113">Indica que la asignación es fundamental para la ejecución de código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8642a-113">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="8642a-114">Este valor se utiliza durante el inicio y al ejecutar los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="8642a-114">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="8642a-115">Si no se puede asignar memoria, CLR no puede funcionar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8642a-115">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="8642a-116">Si se produce un error en la asignación, el CLR se deshabilita en efecto.</span><span class="sxs-lookup"><span data-stu-id="8642a-116">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="8642a-117">Se producirá un error en todas las llamadas subsiguientes a CLR con HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8642a-117">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="8642a-118">Indica que la asignación es fundamental para ejecutar la tarea que ha solicitado la asignación.</span><span class="sxs-lookup"><span data-stu-id="8642a-118">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="8642a-119">Si no se puede asignar memoria, CLR no puede garantizar que la tarea se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="8642a-119">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="8642a-120">En caso de error, CLR genera una <xref:System.Threading.ThreadAbortException> en el subproceso del sistema operativo físico.</span><span class="sxs-lookup"><span data-stu-id="8642a-120">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8642a-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8642a-121">Remarks</span></span>  

 <span data-ttu-id="8642a-122">Los métodos de asignación de memoria definidos en las interfaces [IHostMemoryManager](ihostmemorymanager-interface.md) y [IHostMAlloc](ihostmalloc-interface.md) toman un parámetro de este tipo.</span><span class="sxs-lookup"><span data-stu-id="8642a-122">The memory allocation methods defined in the [IHostMemoryManager](ihostmemorymanager-interface.md) and [IHostMAlloc](ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="8642a-123">Dependiendo de la gravedad de un error, un host puede decidir si se producirá un error de la solicitud de asignación inmediatamente o se esperará hasta que se pueda satisfacer.</span><span class="sxs-lookup"><span data-stu-id="8642a-123">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8642a-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8642a-124">Requirements</span></span>  

 <span data-ttu-id="8642a-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8642a-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8642a-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8642a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8642a-127">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8642a-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8642a-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8642a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8642a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8642a-129">See also</span></span>

- [<span data-ttu-id="8642a-130">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8642a-130">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="8642a-131">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="8642a-131">Hosting Enumerations</span></span>](hosting-enumerations.md)
