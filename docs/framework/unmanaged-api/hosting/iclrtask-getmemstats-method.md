---
description: 'Más información acerca de: ICLRTask:: Getmemstats ((método)'
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
ms.openlocfilehash: ed81e9ced20a43528247d70012077ffd466f9ed1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784982"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="0f3f4-103">ICLRTask::GetMemStats (Método)</span><span class="sxs-lookup"><span data-stu-id="0f3f4-103">ICLRTask::GetMemStats Method</span></span>

<span data-ttu-id="0f3f4-104">Obtiene la información de uso de memoria estadística relacionada con la tarea que la instancia de [ICLRTask](iclrtask-interface.md) actual representa.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-104">Gets statistical memory usage information related to the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f3f4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f3f4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f3f4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f3f4-106">Parameters</span></span>  

 `pMemUsage`  
 <span data-ttu-id="0f3f4-107">enuncia Puntero a una instancia de [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) que contiene los detalles sobre el uso de memoria de la tarea, incluido el número de bytes asignados.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-107">[out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f3f4-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f3f4-108">Return Value</span></span>  
  
|<span data-ttu-id="0f3f4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f3f4-109">HRESULT</span></span>|<span data-ttu-id="0f3f4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f3f4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f3f4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f3f4-111">S_OK</span></span>|<span data-ttu-id="0f3f4-112">`GetMemStats` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-112">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="0f3f4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f3f4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f3f4-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f3f4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f3f4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f3f4-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-116">The call timed out.</span></span>|  
|<span data-ttu-id="0f3f4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f3f4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f3f4-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f3f4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f3f4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f3f4-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f3f4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f3f4-121">E_FAIL</span></span>|<span data-ttu-id="0f3f4-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f3f4-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f3f4-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0f3f4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f3f4-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f3f4-125">Requirements</span></span>  

 <span data-ttu-id="0f3f4-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f3f4-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f3f4-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0f3f4-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f3f4-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f3f4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f3f4-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f3f4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f3f4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f3f4-130">See also</span></span>

- [<span data-ttu-id="0f3f4-131">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f3f4-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0f3f4-132">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f3f4-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0f3f4-133">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f3f4-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0f3f4-134">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f3f4-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
