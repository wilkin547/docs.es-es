---
description: 'Más información acerca de: ICLRTask:: Locksheld ((método)'
title: ICLRTask::LocksHeld (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
ms.openlocfilehash: 5dff0b2a80594e03d61d50c6d9fa52bb12bb42f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799555"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="df609-103">ICLRTask::LocksHeld (Método)</span><span class="sxs-lookup"><span data-stu-id="df609-103">ICLRTask::LocksHeld Method</span></span>

<span data-ttu-id="df609-104">Obtiene el número de bloqueos mantenidos actualmente en la tarea.</span><span class="sxs-lookup"><span data-stu-id="df609-104">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df609-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df609-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df609-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df609-106">Parameters</span></span>  

 `pLockCount`  
 <span data-ttu-id="df609-107">enuncia Número de bloqueos mantenidos en la tarea en el momento de la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="df609-107">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df609-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df609-108">Return Value</span></span>  
  
|<span data-ttu-id="df609-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df609-109">HRESULT</span></span>|<span data-ttu-id="df609-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="df609-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df609-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="df609-111">S_OK</span></span>|<span data-ttu-id="df609-112">`LocksHeld` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="df609-112">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="df609-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df609-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df609-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="df609-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df609-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df609-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df609-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="df609-116">The call timed out.</span></span>|  
|<span data-ttu-id="df609-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df609-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df609-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="df609-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df609-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df609-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df609-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="df609-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df609-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df609-121">E_FAIL</span></span>|<span data-ttu-id="df609-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="df609-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df609-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="df609-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df609-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df609-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df609-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df609-125">Requirements</span></span>  

 <span data-ttu-id="df609-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df609-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df609-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df609-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df609-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df609-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df609-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df609-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df609-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="df609-130">See also</span></span>

- [<span data-ttu-id="df609-131">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df609-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="df609-132">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df609-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="df609-133">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df609-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="df609-134">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df609-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
