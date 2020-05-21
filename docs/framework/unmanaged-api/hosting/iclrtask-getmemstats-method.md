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
ms.openlocfilehash: 0d2975d6247cd9ecdb07b564d77518151404c7d0
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762472"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="936a2-102">ICLRTask::GetMemStats (Método)</span><span class="sxs-lookup"><span data-stu-id="936a2-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="936a2-103">Obtiene la información de uso de memoria estadística relacionada con la tarea que la instancia de [ICLRTask](iclrtask-interface.md) actual representa.</span><span class="sxs-lookup"><span data-stu-id="936a2-103">Gets statistical memory usage information related to the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="936a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="936a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="936a2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="936a2-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="936a2-106">enuncia Puntero a una instancia de [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) que contiene los detalles sobre el uso de memoria de la tarea, incluido el número de bytes asignados.</span><span class="sxs-lookup"><span data-stu-id="936a2-106">[out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="936a2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="936a2-107">Return Value</span></span>  
  
|<span data-ttu-id="936a2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="936a2-108">HRESULT</span></span>|<span data-ttu-id="936a2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="936a2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="936a2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="936a2-110">S_OK</span></span>|<span data-ttu-id="936a2-111">`GetMemStats`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="936a2-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="936a2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="936a2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="936a2-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="936a2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="936a2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="936a2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="936a2-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="936a2-115">The call timed out.</span></span>|  
|<span data-ttu-id="936a2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="936a2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="936a2-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="936a2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="936a2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="936a2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="936a2-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="936a2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="936a2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="936a2-120">E_FAIL</span></span>|<span data-ttu-id="936a2-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="936a2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="936a2-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="936a2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="936a2-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="936a2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="936a2-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="936a2-124">Requirements</span></span>  
 <span data-ttu-id="936a2-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="936a2-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="936a2-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="936a2-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="936a2-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="936a2-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="936a2-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="936a2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936a2-129">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="936a2-129">See also</span></span>

- [<span data-ttu-id="936a2-130">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="936a2-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="936a2-131">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="936a2-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="936a2-132">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="936a2-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="936a2-133">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="936a2-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
