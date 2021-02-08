---
description: 'Más información acerca de: IHostTask:: GetPriority ((método)'
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
ms.openlocfilehash: fb64164a54806a362888e93f031713ccc0ac3578
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784696"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="66670-103">IHostTask::GetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="66670-103">IHostTask::GetPriority Method</span></span>

<span data-ttu-id="66670-104">Obtiene el nivel de prioridad del subproceso de la tarea representada por la instancia de [IHostTask](ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="66670-104">Gets the thread priority level of the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66670-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66670-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66670-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66670-106">Parameters</span></span>  

 `pPriority`  
 <span data-ttu-id="66670-107">enuncia Un puntero a un entero que indica el nivel de prioridad del subproceso de la tarea representada por la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="66670-107">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66670-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="66670-108">Return Value</span></span>  
  
|<span data-ttu-id="66670-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66670-109">HRESULT</span></span>|<span data-ttu-id="66670-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="66670-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66670-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="66670-111">S_OK</span></span>|<span data-ttu-id="66670-112">`GetPriority` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="66670-112">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="66670-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="66670-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="66670-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="66670-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="66670-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="66670-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="66670-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="66670-116">The call timed out.</span></span>|  
|<span data-ttu-id="66670-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="66670-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="66670-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="66670-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="66670-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="66670-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="66670-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="66670-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="66670-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66670-121">E_FAIL</span></span>|<span data-ttu-id="66670-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="66670-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="66670-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="66670-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="66670-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="66670-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66670-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="66670-125">Remarks</span></span>  

 <span data-ttu-id="66670-126">La función de Win32 define los valores de nivel de prioridad del subproceso `SetThreadPriority` .</span><span class="sxs-lookup"><span data-stu-id="66670-126">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66670-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66670-127">Requirements</span></span>  

 <span data-ttu-id="66670-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66670-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66670-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="66670-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66670-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66670-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66670-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66670-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66670-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="66670-132">See also</span></span>

- [<span data-ttu-id="66670-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66670-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="66670-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66670-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="66670-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66670-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="66670-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66670-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
