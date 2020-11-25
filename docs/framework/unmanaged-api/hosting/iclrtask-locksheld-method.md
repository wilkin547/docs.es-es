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
ms.openlocfilehash: 755dfed4107a602390a4402a2dde83e08986b623
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731701"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="51615-102">ICLRTask::LocksHeld (Método)</span><span class="sxs-lookup"><span data-stu-id="51615-102">ICLRTask::LocksHeld Method</span></span>

<span data-ttu-id="51615-103">Obtiene el número de bloqueos mantenidos actualmente en la tarea.</span><span class="sxs-lookup"><span data-stu-id="51615-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51615-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51615-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51615-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51615-105">Parameters</span></span>  

 `pLockCount`  
 <span data-ttu-id="51615-106">enuncia Número de bloqueos mantenidos en la tarea en el momento de la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="51615-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51615-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="51615-107">Return Value</span></span>  
  
|<span data-ttu-id="51615-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51615-108">HRESULT</span></span>|<span data-ttu-id="51615-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="51615-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51615-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="51615-110">S_OK</span></span>|<span data-ttu-id="51615-111">`LocksHeld` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="51615-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="51615-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51615-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51615-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="51615-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51615-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51615-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51615-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="51615-115">The call timed out.</span></span>|  
|<span data-ttu-id="51615-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51615-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51615-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="51615-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51615-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51615-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51615-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="51615-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51615-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51615-120">E_FAIL</span></span>|<span data-ttu-id="51615-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="51615-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51615-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="51615-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51615-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="51615-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51615-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51615-124">Requirements</span></span>  

 <span data-ttu-id="51615-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51615-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51615-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="51615-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51615-127">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51615-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51615-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51615-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51615-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51615-129">See also</span></span>

- [<span data-ttu-id="51615-130">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51615-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="51615-131">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51615-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="51615-132">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51615-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="51615-133">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51615-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
