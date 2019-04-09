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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 702992ab4edfea3f0b699efefedb195cd87586ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136778"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="f82c5-102">IHostTask::GetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="f82c5-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="f82c5-103">Obtiene el nivel de prioridad de subproceso de la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="f82c5-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f82c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f82c5-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f82c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f82c5-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="f82c5-106">[out] Un puntero a un entero que indica el nivel de prioridad de subproceso de la tarea representada por el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="f82c5-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f82c5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f82c5-107">Return Value</span></span>  
  
|<span data-ttu-id="f82c5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f82c5-108">HRESULT</span></span>|<span data-ttu-id="f82c5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f82c5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f82c5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f82c5-110">S_OK</span></span>|`GetPriority` <span data-ttu-id="f82c5-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f82c5-111">returned successfully.</span></span>|  
|<span data-ttu-id="f82c5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f82c5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f82c5-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f82c5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f82c5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f82c5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f82c5-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f82c5-115">The call timed out.</span></span>|  
|<span data-ttu-id="f82c5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f82c5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f82c5-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f82c5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f82c5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f82c5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f82c5-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="f82c5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f82c5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f82c5-120">E_FAIL</span></span>|<span data-ttu-id="f82c5-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="f82c5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f82c5-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="f82c5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f82c5-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f82c5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f82c5-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f82c5-124">Remarks</span></span>  
 <span data-ttu-id="f82c5-125">Definen los valores de nivel de prioridad de subproceso Win32 `SetThreadPriority` función.</span><span class="sxs-lookup"><span data-stu-id="f82c5-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f82c5-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f82c5-126">Requirements</span></span>  
 <span data-ttu-id="f82c5-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f82c5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f82c5-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f82c5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f82c5-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f82c5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f82c5-130">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f82c5-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f82c5-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f82c5-131">See also</span></span>

- [<span data-ttu-id="f82c5-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f82c5-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f82c5-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f82c5-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f82c5-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f82c5-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f82c5-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f82c5-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
