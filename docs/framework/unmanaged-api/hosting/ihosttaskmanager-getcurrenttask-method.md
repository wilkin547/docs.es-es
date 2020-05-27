---
title: IHostTaskManager::GetCurrentTask (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
ms.openlocfilehash: 874951d6b5efed0dc08e6d0e166962767e295c3e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842054"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="5901d-102">IHostTaskManager::GetCurrentTask (Método)</span><span class="sxs-lookup"><span data-stu-id="5901d-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="5901d-103">Obtiene un puntero de interfaz a la tarea que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se realiza esta llamada.</span><span class="sxs-lookup"><span data-stu-id="5901d-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5901d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5901d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5901d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5901d-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="5901d-106">enuncia Puntero a la dirección de una instancia de [IHostTask](ihosttask-interface.md) que representa la tarea que se está ejecutando actualmente, o null, si no se está ejecutando ninguna tarea.</span><span class="sxs-lookup"><span data-stu-id="5901d-106">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5901d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5901d-107">Return Value</span></span>  
  
|<span data-ttu-id="5901d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5901d-108">HRESULT</span></span>|<span data-ttu-id="5901d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5901d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5901d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5901d-110">S_OK</span></span>|<span data-ttu-id="5901d-111">`GetCurrentTask`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5901d-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="5901d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5901d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5901d-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5901d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5901d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5901d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5901d-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5901d-115">The call timed out.</span></span>|  
|<span data-ttu-id="5901d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5901d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5901d-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5901d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5901d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5901d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5901d-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5901d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5901d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5901d-120">E_FAIL</span></span>|<span data-ttu-id="5901d-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5901d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5901d-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5901d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5901d-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5901d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5901d-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="5901d-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="5901d-125">`GetCurrentTask`se llamó a en un subproceso del sistema operativo fuera del control del host.</span><span class="sxs-lookup"><span data-stu-id="5901d-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5901d-126">Notas</span><span class="sxs-lookup"><span data-stu-id="5901d-126">Remarks</span></span>  
 <span data-ttu-id="5901d-127">El host también puede establecer el `pTask` parámetro en null para evitar que una tarea que no ha iniciado no haya entrado en CLR.</span><span class="sxs-lookup"><span data-stu-id="5901d-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5901d-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5901d-128">Requirements</span></span>  
 <span data-ttu-id="5901d-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5901d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5901d-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5901d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5901d-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5901d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5901d-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5901d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5901d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="5901d-133">See also</span></span>

- [<span data-ttu-id="5901d-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5901d-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5901d-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5901d-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5901d-136">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5901d-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5901d-137">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5901d-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
