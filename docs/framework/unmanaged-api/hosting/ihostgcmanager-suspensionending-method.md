---
description: 'Más información sobre: IHostGCManager:: Suspensionending ((método)'
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
ms.openlocfilehash: 43ec3db76e6e6448719f9c40ef2476da4e2ccf9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708629"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="99d51-103">IHostGCManager::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="99d51-103">IHostGCManager::SuspensionEnding Method</span></span>

<span data-ttu-id="99d51-104">Notifica al host que el Common Language Runtime (CLR) está reanudando la ejecución de las tareas en los subprocesos que se han suspendido para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="99d51-104">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d51-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99d51-105">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d51-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99d51-106">Parameters</span></span>  

 `generation`  
 <span data-ttu-id="99d51-107">de La generación de recolección de elementos no utilizados que acaba de finalizar, desde la que se reanuda el subproceso.</span><span class="sxs-lookup"><span data-stu-id="99d51-107">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99d51-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99d51-108">Return Value</span></span>  
  
|<span data-ttu-id="99d51-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99d51-109">HRESULT</span></span>|<span data-ttu-id="99d51-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="99d51-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99d51-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="99d51-111">S_OK</span></span>|<span data-ttu-id="99d51-112">`SuspensionEnding` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="99d51-112">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="99d51-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99d51-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99d51-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="99d51-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99d51-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99d51-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99d51-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="99d51-116">The call timed out.</span></span>|  
|<span data-ttu-id="99d51-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99d51-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99d51-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="99d51-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99d51-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99d51-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99d51-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="99d51-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99d51-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99d51-121">E_FAIL</span></span>|<span data-ttu-id="99d51-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="99d51-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99d51-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="99d51-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99d51-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="99d51-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99d51-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99d51-125">Remarks</span></span>  

 <span data-ttu-id="99d51-126">CLR llama a `SuspensionEnding` después de que realiza una recolección de elementos no utilizados, para informar al host de que el subproceso está reanudando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="99d51-126">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="99d51-127">No vuelva a programar el subproceso desde el que se realizó la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="99d51-127">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d51-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99d51-128">Requirements</span></span>  

 <span data-ttu-id="99d51-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99d51-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d51-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="99d51-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99d51-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99d51-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99d51-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d51-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d51-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="99d51-133">See also</span></span>

- [<span data-ttu-id="99d51-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99d51-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="99d51-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99d51-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="99d51-136">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99d51-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="99d51-137">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99d51-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="99d51-138">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99d51-138">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
