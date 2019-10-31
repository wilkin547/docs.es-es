---
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
ms.openlocfilehash: 6becc44b061ff2baac63437b6a72375d1c3735b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131162"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="42aa8-102">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="42aa8-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="42aa8-103">Describe el conjunto de operaciones para las que un host puede aplicar acciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="42aa8-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42aa8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42aa8-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="42aa8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="42aa8-105">Members</span></span>  
  
|<span data-ttu-id="42aa8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="42aa8-106">Member</span></span>|<span data-ttu-id="42aa8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="42aa8-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="42aa8-108">El host puede especificar acciones de directiva que se deben realizar cuando una <xref:System.AppDomain> se descarga de forma no estable (forzada).</span><span class="sxs-lookup"><span data-stu-id="42aa8-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="42aa8-109">El host puede especificar acciones de directiva que se realizarán cuando se descargue un <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="42aa8-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="42aa8-110">El host puede especificar acciones de directiva que se realizarán cuando se ejecuten los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="42aa8-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="42aa8-111">El host puede especificar acciones de directiva que se realizarán cuando se cierre el proceso.</span><span class="sxs-lookup"><span data-stu-id="42aa8-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="42aa8-112">El host puede especificar acciones de directiva que se deben realizar cuando se anula un subproceso.</span><span class="sxs-lookup"><span data-stu-id="42aa8-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="42aa8-113">El host puede especificar acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región de código crítica.</span><span class="sxs-lookup"><span data-stu-id="42aa8-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="42aa8-114">El host puede especificar acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región de código no crítica.</span><span class="sxs-lookup"><span data-stu-id="42aa8-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42aa8-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42aa8-115">Remarks</span></span>  
 <span data-ttu-id="42aa8-116">La infraestructura de confiabilidad de Common Language Runtime (CLR) distingue entre anulaciones y errores de asignación de recursos que se producen en regiones críticas de código y las que se producen en regiones no críticas de código.</span><span class="sxs-lookup"><span data-stu-id="42aa8-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="42aa8-117">Esta distinción está diseñada para permitir que los hosts establezcan diferentes directivas en función de dónde se produzca un error en el código.</span><span class="sxs-lookup"><span data-stu-id="42aa8-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="42aa8-118">Una *región crítica de código* es cualquier espacio en el que CLR no pueda garantizar que la anulación de una tarea o que no se pueda completar una solicitud de recursos afectará solo a la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="42aa8-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="42aa8-119">Por ejemplo, si una tarea mantiene un bloqueo y recibe un valor HRESULT que indica un error al realizar una solicitud de asignación de memoria, no basta con anular la tarea para garantizar la estabilidad del <xref:System.AppDomain>, ya que la <xref:System.AppDomain> podría contener otras tareas. esperando el mismo bloqueo.</span><span class="sxs-lookup"><span data-stu-id="42aa8-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="42aa8-120">Para abandonar la tarea actual, puede que esas otras tareas dejen de responder.</span><span class="sxs-lookup"><span data-stu-id="42aa8-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="42aa8-121">En tal caso, el host necesita la capacidad de descargar todo el <xref:System.AppDomain> en lugar de arriesgar una posible inestabilidad.</span><span class="sxs-lookup"><span data-stu-id="42aa8-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="42aa8-122">Una *región de código no crítica*, por otro lado, es una región en la que CLR puede garantizar que una anulación o un error solo afectará a la tarea en la que se produce el error.</span><span class="sxs-lookup"><span data-stu-id="42aa8-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="42aa8-123">CLR también distingue entre anulaciones correctas y no correctas (forzada).</span><span class="sxs-lookup"><span data-stu-id="42aa8-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="42aa8-124">En general, una anulación normal o correcta realiza cada esfuerzo para ejecutar rutinas de control de excepciones y finalizadores antes de anular una tarea, mientras que una anulación forzada no realiza ninguna garantía.</span><span class="sxs-lookup"><span data-stu-id="42aa8-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42aa8-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42aa8-125">Requirements</span></span>  
 <span data-ttu-id="42aa8-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42aa8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42aa8-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="42aa8-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42aa8-128">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="42aa8-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42aa8-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42aa8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42aa8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="42aa8-130">See also</span></span>

- [<span data-ttu-id="42aa8-131">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="42aa8-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="42aa8-132">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="42aa8-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="42aa8-133">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42aa8-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="42aa8-134">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42aa8-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="42aa8-135">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="42aa8-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
