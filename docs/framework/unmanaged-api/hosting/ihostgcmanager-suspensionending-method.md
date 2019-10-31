---
title: IHostGCManager::SuspensionEnding (Método)
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
ms.openlocfilehash: 6ef04799c0062c40f1671cbe6d897a148e1b93bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130472"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="40c1e-102">IHostGCManager::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="40c1e-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="40c1e-103">Notifica al host que el Common Language Runtime (CLR) está reanudando la ejecución de las tareas en los subprocesos que se han suspendido para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="40c1e-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40c1e-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40c1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40c1e-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="40c1e-106">de La generación de recolección de elementos no utilizados que acaba de finalizar, desde la que se reanuda el subproceso.</span><span class="sxs-lookup"><span data-stu-id="40c1e-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40c1e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="40c1e-107">Return Value</span></span>  
  
|<span data-ttu-id="40c1e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40c1e-108">HRESULT</span></span>|<span data-ttu-id="40c1e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="40c1e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40c1e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="40c1e-110">S_OK</span></span>|<span data-ttu-id="40c1e-111">`SuspensionEnding` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="40c1e-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="40c1e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40c1e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40c1e-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="40c1e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40c1e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40c1e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40c1e-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="40c1e-115">The call timed out.</span></span>|  
|<span data-ttu-id="40c1e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40c1e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40c1e-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="40c1e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40c1e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40c1e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40c1e-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="40c1e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40c1e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40c1e-120">E_FAIL</span></span>|<span data-ttu-id="40c1e-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="40c1e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40c1e-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="40c1e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40c1e-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="40c1e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40c1e-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40c1e-124">Remarks</span></span>  
 <span data-ttu-id="40c1e-125">CLR llama a `SuspensionEnding` después de realizar una recolección de elementos no utilizados para informar al host de que el subproceso está reanudando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="40c1e-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="40c1e-126">No vuelva a programar el subproceso desde el que se realizó la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="40c1e-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40c1e-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40c1e-127">Requirements</span></span>  
 <span data-ttu-id="40c1e-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40c1e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40c1e-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="40c1e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40c1e-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="40c1e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40c1e-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40c1e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c1e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="40c1e-132">See also</span></span>

- [<span data-ttu-id="40c1e-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c1e-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="40c1e-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c1e-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="40c1e-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c1e-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="40c1e-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c1e-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="40c1e-137">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c1e-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
