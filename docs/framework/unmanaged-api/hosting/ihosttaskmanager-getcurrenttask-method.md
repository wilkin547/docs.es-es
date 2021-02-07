---
description: 'Más información acerca de: IHostTaskManager:: Getcurrenttask ((método)'
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
ms.openlocfilehash: 7e7e516fe4a706fce8b0302f318cfbb164a86eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753814"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="bcf26-103">IHostTaskManager::GetCurrentTask (Método)</span><span class="sxs-lookup"><span data-stu-id="bcf26-103">IHostTaskManager::GetCurrentTask Method</span></span>

<span data-ttu-id="bcf26-104">Obtiene un puntero de interfaz a la tarea que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se realiza esta llamada.</span><span class="sxs-lookup"><span data-stu-id="bcf26-104">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcf26-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcf26-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcf26-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bcf26-106">Parameters</span></span>  

 `pTask`  
 <span data-ttu-id="bcf26-107">enuncia Puntero a la dirección de una instancia de [IHostTask](ihosttask-interface.md) que representa la tarea que se está ejecutando actualmente, o null, si no se está ejecutando ninguna tarea.</span><span class="sxs-lookup"><span data-stu-id="bcf26-107">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcf26-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bcf26-108">Return Value</span></span>  
  
|<span data-ttu-id="bcf26-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bcf26-109">HRESULT</span></span>|<span data-ttu-id="bcf26-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcf26-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bcf26-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bcf26-111">S_OK</span></span>|<span data-ttu-id="bcf26-112">`GetCurrentTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bcf26-112">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="bcf26-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bcf26-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bcf26-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bcf26-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bcf26-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bcf26-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bcf26-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bcf26-116">The call timed out.</span></span>|  
|<span data-ttu-id="bcf26-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bcf26-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bcf26-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bcf26-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bcf26-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bcf26-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bcf26-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="bcf26-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bcf26-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bcf26-121">E_FAIL</span></span>|<span data-ttu-id="bcf26-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="bcf26-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bcf26-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bcf26-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bcf26-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bcf26-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bcf26-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="bcf26-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="bcf26-126">`GetCurrentTask` se llamó a en un subproceso del sistema operativo fuera del control del host.</span><span class="sxs-lookup"><span data-stu-id="bcf26-126">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcf26-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bcf26-127">Remarks</span></span>  

 <span data-ttu-id="bcf26-128">El host también puede establecer el `pTask` parámetro en null para evitar que una tarea que no ha iniciado no haya entrado en CLR.</span><span class="sxs-lookup"><span data-stu-id="bcf26-128">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcf26-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcf26-129">Requirements</span></span>  

 <span data-ttu-id="bcf26-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcf26-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcf26-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bcf26-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bcf26-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bcf26-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcf26-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcf26-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf26-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcf26-134">See also</span></span>

- [<span data-ttu-id="bcf26-135">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bcf26-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="bcf26-136">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bcf26-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="bcf26-137">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bcf26-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="bcf26-138">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bcf26-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
