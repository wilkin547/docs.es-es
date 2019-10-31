---
title: IHostTask::GetPriority (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: 6c33fa6d2e6cb09f013c5334461e61235db549f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121417"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="94468-102">IHostTask::GetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="94468-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="94468-103">Obtiene el nivel de prioridad del subproceso de la tarea representada por la instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="94468-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94468-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94468-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94468-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94468-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="94468-106">enuncia Puntero a un entero que indica el nivel de prioridad del subproceso de la tarea representada por la instancia de `IHostTask` actual.</span><span class="sxs-lookup"><span data-stu-id="94468-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94468-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="94468-107">Return Value</span></span>  
  
|<span data-ttu-id="94468-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94468-108">HRESULT</span></span>|<span data-ttu-id="94468-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="94468-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94468-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="94468-110">S_OK</span></span>|<span data-ttu-id="94468-111">`GetPriority` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="94468-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="94468-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94468-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94468-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="94468-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94468-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94468-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94468-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="94468-115">The call timed out.</span></span>|  
|<span data-ttu-id="94468-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94468-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94468-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="94468-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94468-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94468-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94468-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="94468-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94468-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94468-120">E_FAIL</span></span>|<span data-ttu-id="94468-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="94468-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94468-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="94468-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94468-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="94468-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94468-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94468-124">Remarks</span></span>  
 <span data-ttu-id="94468-125">La función `SetThreadPriority` de Win32 define los valores de nivel de prioridad del subproceso.</span><span class="sxs-lookup"><span data-stu-id="94468-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94468-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94468-126">Requirements</span></span>  
 <span data-ttu-id="94468-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94468-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94468-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94468-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94468-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="94468-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94468-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94468-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94468-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="94468-131">See also</span></span>

- [<span data-ttu-id="94468-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94468-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="94468-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94468-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="94468-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94468-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="94468-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94468-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
