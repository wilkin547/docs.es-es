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
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="a8e8a-102">EMemoryCriticalLevel (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a8e8a-102">EMemoryCriticalLevel Enumeration</span></span>

<span data-ttu-id="a8e8a-103">Contiene valores que indican el impacto de un error cuando se ha solicitado una determinada asignación de memoria, pero no se puede satisfacer.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8e8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8e8a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="a8e8a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a8e8a-105">Members</span></span>  
  
|<span data-ttu-id="a8e8a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a8e8a-106">Member</span></span>|<span data-ttu-id="a8e8a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8e8a-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="a8e8a-108">Indica que la asignación es fundamental para ejecutar el código administrado en el dominio que ha solicitado la asignación.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="a8e8a-109">Si no se puede asignar memoria, CLR no puede garantizar que el dominio siga siendo utilizable.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="a8e8a-110">El host decide qué acción debe realizarse cuando no se puede satisfacer la asignación.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="a8e8a-111">Puede indicar a CLR que anule `AppDomain` automáticamente o que permita que se siga ejecutando llamando a los métodos en [ICLRPolicyManager](iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a8e8a-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="a8e8a-112">Indica que la asignación es fundamental para la ejecución de código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="a8e8a-113">Este valor se utiliza durante el inicio y al ejecutar los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="a8e8a-114">Si no se puede asignar memoria, CLR no puede funcionar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="a8e8a-115">Si se produce un error en la asignación, el CLR se deshabilita en efecto.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="a8e8a-116">Se producirá un error en todas las llamadas subsiguientes a CLR con HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="a8e8a-117">Indica que la asignación es fundamental para ejecutar la tarea que ha solicitado la asignación.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="a8e8a-118">Si no se puede asignar memoria, CLR no puede garantizar que la tarea se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="a8e8a-119">En caso de error, CLR genera una <xref:System.Threading.ThreadAbortException> en el subproceso del sistema operativo físico.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8e8a-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8e8a-120">Remarks</span></span>  

 <span data-ttu-id="a8e8a-121">Los métodos de asignación de memoria definidos en las interfaces [IHostMemoryManager](ihostmemorymanager-interface.md) y [IHostMAlloc](ihostmalloc-interface.md) toman un parámetro de este tipo.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-121">The memory allocation methods defined in the [IHostMemoryManager](ihostmemorymanager-interface.md) and [IHostMAlloc](ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="a8e8a-122">Dependiendo de la gravedad de un error, un host puede decidir si se producirá un error de la solicitud de asignación inmediatamente o se esperará hasta que se pueda satisfacer.</span><span class="sxs-lookup"><span data-stu-id="a8e8a-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8e8a-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8e8a-123">Requirements</span></span>  

 <span data-ttu-id="a8e8a-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8e8a-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8e8a-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a8e8a-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8e8a-126">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8e8a-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8e8a-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8e8a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e8a-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8e8a-128">See also</span></span>

- [<span data-ttu-id="a8e8a-129">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8e8a-129">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="a8e8a-130">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="a8e8a-130">Hosting Enumerations</span></span>](hosting-enumerations.md)
