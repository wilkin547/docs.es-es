---
title: ICLRTask::GetMemStats (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
ms.openlocfilehash: 0bf8b6f393806e590be8f97dbfe2d01d5746c339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139702"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="404c2-102">ICLRTask::GetMemStats (Método)</span><span class="sxs-lookup"><span data-stu-id="404c2-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="404c2-103">Obtiene la información de uso de memoria estadística relacionada con la tarea que la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) actual representa.</span><span class="sxs-lookup"><span data-stu-id="404c2-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="404c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="404c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="404c2-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="404c2-106">enuncia Un puntero a una instancia de [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) que contiene detalles sobre el uso de memoria de la tarea, incluido el número de bytes asignados.</span><span class="sxs-lookup"><span data-stu-id="404c2-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="404c2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="404c2-107">Return Value</span></span>  
  
|<span data-ttu-id="404c2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="404c2-108">HRESULT</span></span>|<span data-ttu-id="404c2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="404c2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="404c2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="404c2-110">S_OK</span></span>|<span data-ttu-id="404c2-111">`GetMemStats` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="404c2-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="404c2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="404c2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="404c2-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="404c2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="404c2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="404c2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="404c2-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="404c2-115">The call timed out.</span></span>|  
|<span data-ttu-id="404c2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="404c2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="404c2-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="404c2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="404c2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="404c2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="404c2-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="404c2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="404c2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="404c2-120">E_FAIL</span></span>|<span data-ttu-id="404c2-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="404c2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="404c2-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="404c2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="404c2-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="404c2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="404c2-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="404c2-124">Requirements</span></span>  
 <span data-ttu-id="404c2-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="404c2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="404c2-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="404c2-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="404c2-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="404c2-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="404c2-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="404c2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404c2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="404c2-129">See also</span></span>

- [<span data-ttu-id="404c2-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="404c2-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="404c2-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="404c2-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="404c2-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="404c2-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="404c2-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="404c2-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
