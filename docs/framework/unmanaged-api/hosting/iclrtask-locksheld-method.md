---
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
ms.openlocfilehash: 3a3c42e2877957e3bbf5031e6ba650e4c9e0364e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195946"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="f3892-102">ICLRTask::LocksHeld (Método)</span><span class="sxs-lookup"><span data-stu-id="f3892-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="f3892-103">Obtiene el número de bloqueos mantenidos actualmente en la tarea.</span><span class="sxs-lookup"><span data-stu-id="f3892-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3892-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3892-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3892-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3892-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="f3892-106">enuncia Número de bloqueos mantenidos en la tarea en el momento de la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="f3892-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3892-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f3892-107">Return Value</span></span>  
  
|<span data-ttu-id="f3892-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f3892-108">HRESULT</span></span>|<span data-ttu-id="f3892-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3892-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f3892-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3892-110">S_OK</span></span>|<span data-ttu-id="f3892-111">`LocksHeld` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3892-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="f3892-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f3892-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f3892-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3892-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f3892-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f3892-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f3892-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f3892-115">The call timed out.</span></span>|  
|<span data-ttu-id="f3892-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f3892-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f3892-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f3892-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f3892-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f3892-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f3892-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f3892-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f3892-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f3892-120">E_FAIL</span></span>|<span data-ttu-id="f3892-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f3892-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f3892-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f3892-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f3892-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f3892-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3892-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3892-124">Requirements</span></span>  
 <span data-ttu-id="f3892-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3892-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3892-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f3892-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3892-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f3892-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3892-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3892-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3892-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3892-129">See also</span></span>

- [<span data-ttu-id="f3892-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3892-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f3892-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3892-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f3892-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3892-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f3892-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3892-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
