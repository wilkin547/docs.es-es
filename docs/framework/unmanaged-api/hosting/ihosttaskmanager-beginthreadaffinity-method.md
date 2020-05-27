---
title: IHostTaskManager::BeginThreadAffinity (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
ms.openlocfilehash: 90ae790603f0e41a20993ffef88654211a3168d9
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842366"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="04233-102">IHostTaskManager::BeginThreadAffinity (Método)</span><span class="sxs-lookup"><span data-stu-id="04233-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="04233-103">Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="04233-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04233-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04233-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="04233-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04233-105">Return Value</span></span>  
  
|<span data-ttu-id="04233-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04233-106">HRESULT</span></span>|<span data-ttu-id="04233-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="04233-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04233-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="04233-108">S_OK</span></span>|<span data-ttu-id="04233-109">`BeginThreadAffinity`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="04233-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="04233-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04233-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04233-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="04233-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04233-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04233-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04233-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04233-113">The call timed out.</span></span>|  
|<span data-ttu-id="04233-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04233-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04233-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="04233-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04233-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04233-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04233-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="04233-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04233-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04233-118">E_FAIL</span></span>|<span data-ttu-id="04233-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="04233-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04233-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="04233-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04233-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="04233-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04233-122">Notas</span><span class="sxs-lookup"><span data-stu-id="04233-122">Remarks</span></span>  
 <span data-ttu-id="04233-123">CLR normalmente llama a `IHostTaskManager::BeginThreadAffinity` en el contexto de una llamada a <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="04233-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="04233-124">La tarea actual no se debe volver a programar hasta que se realice una llamada correspondiente a [IHostTaskManager:: EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="04233-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="04233-125">Las tareas se pueden desactivar, pero cuando se vuelven a cambiar, deben asignarse al mismo subproceso del sistema operativo desde el que se han desactivado. Las llamadas anidadas a `BeginThreadAffinity` no tienen ningún efecto, ya que la llamada hace referencia a la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="04233-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04233-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04233-126">Requirements</span></span>  
 <span data-ttu-id="04233-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04233-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04233-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04233-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04233-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04233-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04233-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04233-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04233-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="04233-131">See also</span></span>

- [<span data-ttu-id="04233-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04233-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="04233-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04233-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="04233-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04233-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="04233-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04233-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
