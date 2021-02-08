---
description: 'Más información acerca de: IHostTask:: join (método)'
title: IHostTask::Join (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
ms.openlocfilehash: 8231401ab01ee040f225b78a52b61eb7d59af1d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784657"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="5eb79-103">IHostTask::Join (Método)</span><span class="sxs-lookup"><span data-stu-id="5eb79-103">IHostTask::Join Method</span></span>

<span data-ttu-id="5eb79-104">Bloquea la tarea que realiza la llamada hasta que se completa la tarea representada por la instancia actual de [IHostTask](ihosttask-interface.md) , transcurre el intervalo de tiempo especificado o se llama a [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5eb79-104">Blocks the calling task until the task represented by the current [IHostTask](ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5eb79-105">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5eb79-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5eb79-106">Parameters</span></span>  

 `milliseconds`  
 <span data-ttu-id="5eb79-107">de Intervalo de tiempo, en milisegundos, que se va a esperar a que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="5eb79-107">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="5eb79-108">Si este intervalo transcurre antes de que finalice la tarea, la tarea que realiza la llamada se desbloquea.</span><span class="sxs-lookup"><span data-stu-id="5eb79-108">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="5eb79-109">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="5eb79-109">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values.</span></span> <span data-ttu-id="5eb79-110">Un valor de WAIT_ALERTABLE indica al host que reactive la tarea si `Alert` se llama a antes de que `milliseconds` transcurra.</span><span class="sxs-lookup"><span data-stu-id="5eb79-110">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5eb79-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5eb79-111">Return Value</span></span>  
  
|<span data-ttu-id="5eb79-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5eb79-112">HRESULT</span></span>|<span data-ttu-id="5eb79-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5eb79-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5eb79-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5eb79-114">S_OK</span></span>|<span data-ttu-id="5eb79-115">`Join` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5eb79-115">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="5eb79-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5eb79-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5eb79-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5eb79-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5eb79-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5eb79-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5eb79-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5eb79-119">The call timed out.</span></span>|  
|<span data-ttu-id="5eb79-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5eb79-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5eb79-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5eb79-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5eb79-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5eb79-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5eb79-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él, o bien la `IHostTask` instancia actual no está asociada a una tarea.</span><span class="sxs-lookup"><span data-stu-id="5eb79-123">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="5eb79-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5eb79-124">E_FAIL</span></span>|<span data-ttu-id="5eb79-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5eb79-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5eb79-126">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5eb79-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5eb79-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5eb79-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5eb79-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5eb79-128">Requirements</span></span>  

 <span data-ttu-id="5eb79-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5eb79-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eb79-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5eb79-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5eb79-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5eb79-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5eb79-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eb79-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb79-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="5eb79-133">See also</span></span>

- [<span data-ttu-id="5eb79-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5eb79-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="5eb79-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5eb79-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="5eb79-136">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5eb79-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="5eb79-137">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5eb79-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="5eb79-138">WAIT_OPTION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5eb79-138">WAIT_OPTION Enumeration</span></span>](wait-option-enumeration.md)
