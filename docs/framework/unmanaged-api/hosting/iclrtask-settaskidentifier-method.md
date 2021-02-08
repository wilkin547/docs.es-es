---
description: 'Más información acerca de: ICLRTask:: Settaskidentifier ((método)'
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
ms.openlocfilehash: e746d8ec96d16f7761dd49ac814ddbed073c2686
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784956"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="3bf11-103">ICLRTask::SetTaskIdentifier (Método)</span><span class="sxs-lookup"><span data-stu-id="3bf11-103">ICLRTask::SetTaskIdentifier Method</span></span>

<span data-ttu-id="3bf11-104">Indica al Common Language Runtime (CLR) que asocie el valor de identificador especificado a la tarea representada por la instancia de [ICLRTask](iclrtask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="3bf11-104">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bf11-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bf11-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bf11-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bf11-106">Parameters</span></span>  

 `Asked`  
 <span data-ttu-id="3bf11-107">de Identificador único del Common Language Runtime que se va a asociar a la tarea representada por la `ICLRTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="3bf11-107">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bf11-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3bf11-108">Return Value</span></span>  
  
|<span data-ttu-id="3bf11-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3bf11-109">HRESULT</span></span>|<span data-ttu-id="3bf11-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3bf11-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bf11-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bf11-111">S_OK</span></span>|<span data-ttu-id="3bf11-112">`SetTaskIdentifier` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3bf11-112">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="3bf11-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3bf11-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3bf11-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3bf11-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3bf11-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3bf11-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3bf11-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3bf11-116">The call timed out.</span></span>|  
|<span data-ttu-id="3bf11-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3bf11-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3bf11-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3bf11-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3bf11-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3bf11-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3bf11-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3bf11-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3bf11-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3bf11-121">E_FAIL</span></span>|<span data-ttu-id="3bf11-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3bf11-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3bf11-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3bf11-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3bf11-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3bf11-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bf11-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3bf11-125">Remarks</span></span>  

 <span data-ttu-id="3bf11-126">El host puede asociar un identificador a una tarea para facilitar la integración de CLR y el host en un entorno de depuración.</span><span class="sxs-lookup"><span data-stu-id="3bf11-126">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="3bf11-127">El identificador no tiene ningún significado para CLR.</span><span class="sxs-lookup"><span data-stu-id="3bf11-127">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="3bf11-128">El CLR lo pasa a una aplicación del depurador.</span><span class="sxs-lookup"><span data-stu-id="3bf11-128">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="3bf11-129">El depurador puede usar este identificador para asociar una pila de llamadas de CLR a una pila de llamadas de host y permitir que la información de seguimiento respectiva sea unificada cuando se ve en la interfaz de usuario del depurador.</span><span class="sxs-lookup"><span data-stu-id="3bf11-129">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bf11-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bf11-130">Requirements</span></span>  

 <span data-ttu-id="3bf11-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bf11-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bf11-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3bf11-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bf11-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3bf11-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bf11-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bf11-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf11-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bf11-135">See also</span></span>

- [<span data-ttu-id="3bf11-136">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bf11-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="3bf11-137">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bf11-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="3bf11-138">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bf11-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="3bf11-139">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bf11-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
