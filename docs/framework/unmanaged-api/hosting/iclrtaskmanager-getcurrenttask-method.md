---
description: 'Más información acerca de: ICLRTaskManager:: Getcurrenttask ((método)'
title: ICLRTaskManager::GetCurrentTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: d7435f9099d6a8ceb173afbf79c1d0f5d4005980
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728553"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="b8e92-103">ICLRTaskManager::GetCurrentTask (Método)</span><span class="sxs-lookup"><span data-stu-id="b8e92-103">ICLRTaskManager::GetCurrentTask Method</span></span>

<span data-ttu-id="b8e92-104">Obtiene la instancia de [ICLRTask](iclrtask-interface.md) que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se originó la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="b8e92-104">Gets the [ICLRTask](iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e92-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8e92-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e92-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8e92-106">Parameters</span></span>  

 `ppTask`  
 <span data-ttu-id="b8e92-107">enuncia Puntero a la dirección de una `ICLRTask` instancia de que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se originó la llamada, o null si no hay ninguna tarea en ejecución actualmente en este subproceso.</span><span class="sxs-lookup"><span data-stu-id="b8e92-107">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8e92-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8e92-108">Return Value</span></span>  
  
|<span data-ttu-id="b8e92-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8e92-109">HRESULT</span></span>|<span data-ttu-id="b8e92-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8e92-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8e92-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8e92-111">S_OK</span></span>|<span data-ttu-id="b8e92-112">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8e92-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="b8e92-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b8e92-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8e92-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8e92-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b8e92-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b8e92-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b8e92-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b8e92-116">The call timed out.</span></span>|  
|<span data-ttu-id="b8e92-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8e92-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b8e92-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b8e92-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b8e92-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b8e92-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b8e92-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="b8e92-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b8e92-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8e92-121">E_FAIL</span></span>|<span data-ttu-id="b8e92-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b8e92-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b8e92-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b8e92-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b8e92-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b8e92-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8e92-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b8e92-125">Remarks</span></span>  

 <span data-ttu-id="b8e92-126">La `ICLRTask` instancia a la que `ppTask` apunta el parámetro representa la tarea que se está ejecutando actualmente para CLR.</span><span class="sxs-lookup"><span data-stu-id="b8e92-126">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="b8e92-127">La `ICLRTask` instancia de está asociada a una instancia de [IHostTask](ihosttask-interface.md) correspondiente que representa la tarea para el host.</span><span class="sxs-lookup"><span data-stu-id="b8e92-127">The `ICLRTask` instance is associated with a corresponding [IHostTask](ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e92-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8e92-128">Requirements</span></span>  

 <span data-ttu-id="b8e92-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8e92-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e92-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b8e92-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8e92-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8e92-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8e92-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e92-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e92-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8e92-133">See also</span></span>

- [<span data-ttu-id="b8e92-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8e92-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b8e92-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8e92-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b8e92-136">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8e92-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b8e92-137">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8e92-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
