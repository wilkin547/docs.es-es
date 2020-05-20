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
ms.openlocfilehash: e7cb1c2070e760258e548d2f45e3b6ed11e046c4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616326"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="07f87-102">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="07f87-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="07f87-103">Describe el conjunto de operaciones para las que un host puede aplicar acciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="07f87-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07f87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07f87-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="07f87-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="07f87-105">Members</span></span>  
  
|<span data-ttu-id="07f87-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="07f87-106">Member</span></span>|<span data-ttu-id="07f87-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="07f87-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="07f87-108">El host puede especificar acciones de directiva que deben realizarse cuando un <xref:System.AppDomain> se descarga de forma no estable (forzada).</span><span class="sxs-lookup"><span data-stu-id="07f87-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="07f87-109">El host puede especificar acciones de directiva que se deben realizar cuando <xref:System.AppDomain> se descarga un.</span><span class="sxs-lookup"><span data-stu-id="07f87-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="07f87-110">El host puede especificar acciones de directiva que se realizarán cuando se ejecuten los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="07f87-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="07f87-111">El host puede especificar acciones de directiva que se realizarán cuando se cierre el proceso.</span><span class="sxs-lookup"><span data-stu-id="07f87-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="07f87-112">El host puede especificar acciones de directiva que se deben realizar cuando se anula un subproceso.</span><span class="sxs-lookup"><span data-stu-id="07f87-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="07f87-113">El host puede especificar acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región de código crítica.</span><span class="sxs-lookup"><span data-stu-id="07f87-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="07f87-114">El host puede especificar acciones de directiva que se deben realizar cuando se produce una anulación de subproceso forzada en una región de código no crítica.</span><span class="sxs-lookup"><span data-stu-id="07f87-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07f87-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="07f87-115">Remarks</span></span>  
 <span data-ttu-id="07f87-116">La infraestructura de confiabilidad de Common Language Runtime (CLR) distingue entre anulaciones y errores de asignación de recursos que se producen en regiones críticas de código y las que se producen en regiones no críticas de código.</span><span class="sxs-lookup"><span data-stu-id="07f87-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="07f87-117">Esta distinción está diseñada para permitir que los hosts establezcan diferentes directivas en función de dónde se produzca un error en el código.</span><span class="sxs-lookup"><span data-stu-id="07f87-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="07f87-118">Una *región crítica de código* es cualquier espacio en el que CLR no pueda garantizar que la anulación de una tarea o que no se pueda completar una solicitud de recursos afectará solo a la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="07f87-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="07f87-119">Por ejemplo, si una tarea está manteniendo un bloqueo y recibe un valor HRESULT que indica un error al realizar una solicitud de asignación de memoria, no basta con anular la tarea para garantizar la estabilidad de <xref:System.AppDomain> , ya que <xref:System.AppDomain> puede contener otras tareas que esperan el mismo bloqueo.</span><span class="sxs-lookup"><span data-stu-id="07f87-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="07f87-120">Para abandonar la tarea actual, puede que esas otras tareas dejen de responder.</span><span class="sxs-lookup"><span data-stu-id="07f87-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="07f87-121">En tal caso, el host necesita la capacidad de descargar todo <xref:System.AppDomain> en lugar de riesgo potencial de inestabilidad.</span><span class="sxs-lookup"><span data-stu-id="07f87-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="07f87-122">Una *región de código no crítica*, por otro lado, es una región en la que CLR puede garantizar que una anulación o un error solo afectará a la tarea en la que se produce el error.</span><span class="sxs-lookup"><span data-stu-id="07f87-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="07f87-123">CLR también distingue entre anulaciones correctas y no correctas (forzada).</span><span class="sxs-lookup"><span data-stu-id="07f87-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="07f87-124">En general, una anulación normal o correcta realiza cada esfuerzo para ejecutar rutinas de control de excepciones y finalizadores antes de anular una tarea, mientras que una anulación forzada no realiza ninguna garantía.</span><span class="sxs-lookup"><span data-stu-id="07f87-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07f87-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07f87-125">Requirements</span></span>  
 <span data-ttu-id="07f87-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07f87-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07f87-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="07f87-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07f87-128">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="07f87-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07f87-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07f87-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f87-130">Consulta también</span><span class="sxs-lookup"><span data-stu-id="07f87-130">See also</span></span>

- [<span data-ttu-id="07f87-131">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="07f87-131">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="07f87-132">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="07f87-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="07f87-133">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07f87-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="07f87-134">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07f87-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="07f87-135">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="07f87-135">Hosting Enumerations</span></span>](hosting-enumerations.md)
