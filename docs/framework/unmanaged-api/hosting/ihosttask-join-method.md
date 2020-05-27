---
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
ms.openlocfilehash: 8fa59e065042565b4a543106fff714558cef42ec
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842249"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="82ad3-102">IHostTask::Join (Método)</span><span class="sxs-lookup"><span data-stu-id="82ad3-102">IHostTask::Join Method</span></span>
<span data-ttu-id="82ad3-103">Bloquea la tarea que realiza la llamada hasta que se completa la tarea representada por la instancia actual de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , transcurre el intervalo de tiempo especificado o se llama a [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="82ad3-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82ad3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82ad3-104">Syntax</span></span>  
  
```cpp  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82ad3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82ad3-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="82ad3-106">de Intervalo de tiempo, en milisegundos, que se va a esperar a que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="82ad3-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="82ad3-107">Si este intervalo transcurre antes de que finalice la tarea, la tarea que realiza la llamada se desbloquea.</span><span class="sxs-lookup"><span data-stu-id="82ad3-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="82ad3-108">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="82ad3-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values.</span></span> <span data-ttu-id="82ad3-109">Un valor de WAIT_ALERTABLE indica al host que reactive la tarea si `Alert` se llama a antes de que `milliseconds` transcurra.</span><span class="sxs-lookup"><span data-stu-id="82ad3-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82ad3-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="82ad3-110">Return Value</span></span>  
  
|<span data-ttu-id="82ad3-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82ad3-111">HRESULT</span></span>|<span data-ttu-id="82ad3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="82ad3-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82ad3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="82ad3-113">S_OK</span></span>|<span data-ttu-id="82ad3-114">`Join`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="82ad3-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="82ad3-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82ad3-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82ad3-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="82ad3-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82ad3-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82ad3-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82ad3-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="82ad3-118">The call timed out.</span></span>|  
|<span data-ttu-id="82ad3-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82ad3-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82ad3-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="82ad3-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82ad3-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82ad3-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82ad3-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él, o bien la `IHostTask` instancia actual no está asociada a una tarea.</span><span class="sxs-lookup"><span data-stu-id="82ad3-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="82ad3-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82ad3-123">E_FAIL</span></span>|<span data-ttu-id="82ad3-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="82ad3-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82ad3-125">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="82ad3-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82ad3-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="82ad3-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82ad3-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82ad3-127">Requirements</span></span>  
 <span data-ttu-id="82ad3-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82ad3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82ad3-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="82ad3-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82ad3-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="82ad3-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82ad3-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82ad3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ad3-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="82ad3-132">See also</span></span>

- [<span data-ttu-id="82ad3-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82ad3-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="82ad3-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82ad3-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="82ad3-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82ad3-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="82ad3-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82ad3-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="82ad3-137">WAIT_OPTION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="82ad3-137">WAIT_OPTION Enumeration</span></span>](wait-option-enumeration.md)
