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
ms.openlocfilehash: d1d6ddfe7834a1c6f22b9195042d32363d6ea6cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133042"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="abe3e-102">IHostTaskManager::GetCurrentTask (Método)</span><span class="sxs-lookup"><span data-stu-id="abe3e-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="abe3e-103">Obtiene un puntero de interfaz a la tarea que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se realiza esta llamada.</span><span class="sxs-lookup"><span data-stu-id="abe3e-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abe3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abe3e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abe3e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abe3e-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="abe3e-106">enuncia Puntero a la dirección de una instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) que representa la tarea que se está ejecutando actualmente, o null, si no se está ejecutando ninguna tarea.</span><span class="sxs-lookup"><span data-stu-id="abe3e-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abe3e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="abe3e-107">Return Value</span></span>  
  
|<span data-ttu-id="abe3e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="abe3e-108">HRESULT</span></span>|<span data-ttu-id="abe3e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="abe3e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abe3e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="abe3e-110">S_OK</span></span>|<span data-ttu-id="abe3e-111">`GetCurrentTask` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="abe3e-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="abe3e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="abe3e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="abe3e-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="abe3e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="abe3e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="abe3e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="abe3e-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="abe3e-115">The call timed out.</span></span>|  
|<span data-ttu-id="abe3e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="abe3e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="abe3e-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="abe3e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="abe3e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="abe3e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="abe3e-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="abe3e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="abe3e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="abe3e-120">E_FAIL</span></span>|<span data-ttu-id="abe3e-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="abe3e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="abe3e-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="abe3e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="abe3e-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="abe3e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="abe3e-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="abe3e-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="abe3e-125">se llamó a `GetCurrentTask` en un subproceso del sistema operativo fuera del control del host.</span><span class="sxs-lookup"><span data-stu-id="abe3e-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abe3e-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abe3e-126">Remarks</span></span>  
 <span data-ttu-id="abe3e-127">El host también puede establecer el parámetro `pTask` en null para evitar que una tarea que no ha iniciado no haya entrado en CLR.</span><span class="sxs-lookup"><span data-stu-id="abe3e-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abe3e-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abe3e-128">Requirements</span></span>  
 <span data-ttu-id="abe3e-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abe3e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abe3e-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="abe3e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abe3e-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="abe3e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abe3e-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abe3e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe3e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="abe3e-133">See also</span></span>

- [<span data-ttu-id="abe3e-134">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abe3e-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="abe3e-135">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abe3e-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="abe3e-136">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abe3e-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="abe3e-137">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abe3e-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
