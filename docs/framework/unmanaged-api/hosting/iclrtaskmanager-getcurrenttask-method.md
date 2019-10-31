---
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
ms.openlocfilehash: a57610d1b41d80d54a245b9744aafd78a1e88177
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195906"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="48db1-102">ICLRTaskManager::GetCurrentTask (Método)</span><span class="sxs-lookup"><span data-stu-id="48db1-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="48db1-103">Obtiene la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se originó la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="48db1-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48db1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48db1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48db1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48db1-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="48db1-106">enuncia Puntero a la dirección de una instancia de `ICLRTask` que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se originó la llamada, o null si no hay ninguna tarea que se esté ejecutando actualmente en este subproceso.</span><span class="sxs-lookup"><span data-stu-id="48db1-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48db1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="48db1-107">Return Value</span></span>  
  
|<span data-ttu-id="48db1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48db1-108">HRESULT</span></span>|<span data-ttu-id="48db1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="48db1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48db1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="48db1-110">S_OK</span></span>|<span data-ttu-id="48db1-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="48db1-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="48db1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48db1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48db1-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="48db1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48db1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48db1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48db1-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="48db1-115">The call timed out.</span></span>|  
|<span data-ttu-id="48db1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48db1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48db1-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="48db1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48db1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48db1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48db1-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="48db1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48db1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48db1-120">E_FAIL</span></span>|<span data-ttu-id="48db1-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="48db1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48db1-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="48db1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48db1-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="48db1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48db1-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="48db1-124">Remarks</span></span>  
 <span data-ttu-id="48db1-125">La instancia de `ICLRTask` a la que apunta el parámetro `ppTask` representa la tarea que se está ejecutando actualmente para CLR.</span><span class="sxs-lookup"><span data-stu-id="48db1-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="48db1-126">La instancia de `ICLRTask` está asociada a una instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) correspondiente que representa la tarea para el host.</span><span class="sxs-lookup"><span data-stu-id="48db1-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48db1-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48db1-127">Requirements</span></span>  
 <span data-ttu-id="48db1-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48db1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48db1-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="48db1-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48db1-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="48db1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48db1-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48db1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48db1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="48db1-132">See also</span></span>

- [<span data-ttu-id="48db1-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48db1-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="48db1-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48db1-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="48db1-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48db1-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="48db1-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48db1-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
