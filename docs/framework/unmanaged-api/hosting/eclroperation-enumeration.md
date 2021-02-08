---
description: 'Más información sobre: EClrOperation (enumeración)'
title: EClrOperation (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: 9f75762a400955b5f36fb2a337f283e36a32658c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785567"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="eed00-103">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eed00-103">EClrOperation Enumeration</span></span>

<span data-ttu-id="eed00-104">Describe el conjunto de operaciones para las que un host puede aplicar acciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="eed00-104">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eed00-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eed00-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="eed00-106">Members</span><span class="sxs-lookup"><span data-stu-id="eed00-106">Members</span></span>  
  
|<span data-ttu-id="eed00-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="eed00-107">Member</span></span>|<span data-ttu-id="eed00-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="eed00-108">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="eed00-109">El host puede especificar acciones de directiva que deben realizarse cuando un <xref:System.AppDomain> se descarga de forma no estable (forzada).</span><span class="sxs-lookup"><span data-stu-id="eed00-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="eed00-110">El host puede especificar acciones de directiva que se deben realizar cuando <xref:System.AppDomain> se descarga un.</span><span class="sxs-lookup"><span data-stu-id="eed00-110">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="eed00-111">El host puede especificar acciones de directiva que se realizarán cuando se ejecuten los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="eed00-111">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="eed00-112">El host puede especificar acciones de directiva que se realizarán cuando se cierre el proceso.</span><span class="sxs-lookup"><span data-stu-id="eed00-112">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="eed00-113">El host puede especificar acciones de directiva que se deben realizar cuando se anula un subproceso.</span><span class="sxs-lookup"><span data-stu-id="eed00-113">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="eed00-114">El host puede especificar acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región de código crítica.</span><span class="sxs-lookup"><span data-stu-id="eed00-114">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="eed00-115">El host puede especificar acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región de código no crítica.</span><span class="sxs-lookup"><span data-stu-id="eed00-115">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eed00-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eed00-116">Remarks</span></span>  

 <span data-ttu-id="eed00-117">La infraestructura de confiabilidad de Common Language Runtime (CLR) distingue entre anulaciones y errores de asignación de recursos que se producen en regiones críticas de código y las que se producen en regiones no críticas de código.</span><span class="sxs-lookup"><span data-stu-id="eed00-117">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="eed00-118">Esta distinción está diseñada para permitir que los hosts establezcan diferentes directivas en función de dónde se produzca un error en el código.</span><span class="sxs-lookup"><span data-stu-id="eed00-118">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="eed00-119">Una *región crítica de código* es cualquier espacio en el que CLR no pueda garantizar que la anulación de una tarea o que no se pueda completar una solicitud de recursos afectará solo a la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="eed00-119">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="eed00-120">Por ejemplo, si una tarea está manteniendo un bloqueo y recibe un valor HRESULT que indica un error al realizar una solicitud de asignación de memoria, no basta con anular la tarea para garantizar la estabilidad de <xref:System.AppDomain> , ya que <xref:System.AppDomain> puede contener otras tareas que esperan el mismo bloqueo.</span><span class="sxs-lookup"><span data-stu-id="eed00-120">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="eed00-121">Para abandonar la tarea actual, puede que esas otras tareas dejen de responder.</span><span class="sxs-lookup"><span data-stu-id="eed00-121">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="eed00-122">En tal caso, el host necesita la capacidad de descargar todo <xref:System.AppDomain> en lugar de riesgo potencial de inestabilidad.</span><span class="sxs-lookup"><span data-stu-id="eed00-122">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="eed00-123">Una *región de código no crítica*, por otro lado, es una región en la que CLR puede garantizar que una anulación o un error solo afectará a la tarea en la que se produce el error.</span><span class="sxs-lookup"><span data-stu-id="eed00-123">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="eed00-124">CLR también distingue entre anulaciones correctas y no correctas (forzada).</span><span class="sxs-lookup"><span data-stu-id="eed00-124">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="eed00-125">En general, una anulación normal o correcta realiza cada esfuerzo para ejecutar rutinas de control de excepciones y finalizadores antes de anular una tarea, mientras que una anulación forzada no realiza ninguna garantía.</span><span class="sxs-lookup"><span data-stu-id="eed00-125">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eed00-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eed00-126">Requirements</span></span>  

 <span data-ttu-id="eed00-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eed00-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eed00-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eed00-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eed00-129">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eed00-129">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eed00-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eed00-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed00-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="eed00-131">See also</span></span>

- [<span data-ttu-id="eed00-132">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eed00-132">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="eed00-133">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="eed00-133">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="eed00-134">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eed00-134">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="eed00-135">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eed00-135">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="eed00-136">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="eed00-136">Hosting Enumerations</span></span>](hosting-enumerations.md)
