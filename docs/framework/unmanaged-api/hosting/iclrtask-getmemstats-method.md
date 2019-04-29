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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 668e570c315f5473f222905a061f05ac94afa81a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763573"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="795de-102">ICLRTask::GetMemStats (Método)</span><span class="sxs-lookup"><span data-stu-id="795de-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="795de-103">Obtiene la información de uso de memoria estadísticas relacionadas con la tarea que actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) representa la instancia.</span><span class="sxs-lookup"><span data-stu-id="795de-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="795de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="795de-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="795de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="795de-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="795de-106">[out] Un puntero a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instancia que contiene detalles sobre el uso de memoria de la tarea, incluido el número de bytes asignados.</span><span class="sxs-lookup"><span data-stu-id="795de-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="795de-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="795de-107">Return Value</span></span>  
  
|<span data-ttu-id="795de-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="795de-108">HRESULT</span></span>|<span data-ttu-id="795de-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="795de-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="795de-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="795de-110">S_OK</span></span>|<span data-ttu-id="795de-111">`GetMemStats` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="795de-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="795de-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="795de-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="795de-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="795de-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="795de-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="795de-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="795de-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="795de-115">The call timed out.</span></span>|  
|<span data-ttu-id="795de-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="795de-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="795de-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="795de-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="795de-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="795de-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="795de-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="795de-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="795de-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="795de-120">E_FAIL</span></span>|<span data-ttu-id="795de-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="795de-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="795de-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="795de-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="795de-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="795de-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="795de-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="795de-124">Requirements</span></span>  
 <span data-ttu-id="795de-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="795de-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="795de-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="795de-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="795de-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="795de-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="795de-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="795de-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="795de-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="795de-129">See also</span></span>

- [<span data-ttu-id="795de-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="795de-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="795de-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="795de-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="795de-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="795de-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="795de-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="795de-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
