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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f548d8b19a76aaccbae276dd63f091e4488690b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106813"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="cda20-102">ICLRTask::LocksHeld (Método)</span><span class="sxs-lookup"><span data-stu-id="cda20-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="cda20-103">Obtiene el número de bloqueos mantenidos en la tarea.</span><span class="sxs-lookup"><span data-stu-id="cda20-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda20-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cda20-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cda20-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cda20-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="cda20-106">[out] El número de bloqueos mantenidos en la tarea en el momento de la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="cda20-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cda20-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cda20-107">Return Value</span></span>  
  
|<span data-ttu-id="cda20-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cda20-108">HRESULT</span></span>|<span data-ttu-id="cda20-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cda20-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cda20-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cda20-110">S_OK</span></span>|`LocksHeld` <span data-ttu-id="cda20-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cda20-111">returned successfully.</span></span>|  
|<span data-ttu-id="cda20-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cda20-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cda20-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="cda20-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cda20-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cda20-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cda20-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="cda20-115">The call timed out.</span></span>|  
|<span data-ttu-id="cda20-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cda20-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cda20-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cda20-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cda20-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cda20-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cda20-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="cda20-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cda20-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cda20-120">E_FAIL</span></span>|<span data-ttu-id="cda20-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="cda20-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cda20-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="cda20-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cda20-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cda20-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cda20-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cda20-124">Requirements</span></span>  
 <span data-ttu-id="cda20-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cda20-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cda20-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cda20-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cda20-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cda20-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cda20-128">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cda20-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cda20-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="cda20-129">See also</span></span>

- [<span data-ttu-id="cda20-130">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cda20-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="cda20-131">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cda20-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="cda20-132">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cda20-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="cda20-133">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cda20-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
