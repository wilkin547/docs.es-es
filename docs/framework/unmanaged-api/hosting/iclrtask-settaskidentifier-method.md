---
title: ICLRTask::SetTaskIdentifier (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: d1f731e00d4917b997dfba392cb9b6ce2afc082e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690751"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="33914-102">ICLRTask::SetTaskIdentifier (Método)</span><span class="sxs-lookup"><span data-stu-id="33914-102">ICLRTask::SetTaskIdentifier Method</span></span>

<span data-ttu-id="33914-103">Indica al Common Language Runtime (CLR) que asocie el valor de identificador especificado a la tarea representada por la instancia de [ICLRTask](iclrtask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="33914-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33914-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33914-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33914-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33914-105">Parameters</span></span>  

 `Asked`  
 <span data-ttu-id="33914-106">de Identificador único del Common Language Runtime que se va a asociar a la tarea representada por la `ICLRTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="33914-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33914-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33914-107">Return Value</span></span>  
  
|<span data-ttu-id="33914-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33914-108">HRESULT</span></span>|<span data-ttu-id="33914-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="33914-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33914-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="33914-110">S_OK</span></span>|<span data-ttu-id="33914-111">`SetTaskIdentifier` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="33914-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="33914-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="33914-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="33914-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="33914-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="33914-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="33914-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="33914-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="33914-115">The call timed out.</span></span>|  
|<span data-ttu-id="33914-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="33914-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="33914-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="33914-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="33914-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="33914-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="33914-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="33914-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="33914-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="33914-120">E_FAIL</span></span>|<span data-ttu-id="33914-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="33914-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="33914-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="33914-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="33914-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="33914-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33914-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33914-124">Remarks</span></span>  

 <span data-ttu-id="33914-125">El host puede asociar un identificador a una tarea para facilitar la integración de CLR y el host en un entorno de depuración.</span><span class="sxs-lookup"><span data-stu-id="33914-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="33914-126">El identificador no tiene ningún significado para CLR.</span><span class="sxs-lookup"><span data-stu-id="33914-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="33914-127">El CLR lo pasa a una aplicación del depurador.</span><span class="sxs-lookup"><span data-stu-id="33914-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="33914-128">El depurador puede usar este identificador para asociar una pila de llamadas de CLR a una pila de llamadas de host y permitir que la información de seguimiento respectiva sea unificada cuando se ve en la interfaz de usuario del depurador.</span><span class="sxs-lookup"><span data-stu-id="33914-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33914-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33914-129">Requirements</span></span>  

 <span data-ttu-id="33914-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33914-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33914-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="33914-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33914-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33914-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33914-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33914-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33914-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33914-134">See also</span></span>

- [<span data-ttu-id="33914-135">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33914-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="33914-136">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33914-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="33914-137">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33914-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="33914-138">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33914-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
