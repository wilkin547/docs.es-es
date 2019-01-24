---
title: IHostTaskManager::Sleep (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9661d1cd6994acf2c622350593ede502929f3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510655"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="43785-102">IHostTaskManager::Sleep (Método)</span><span class="sxs-lookup"><span data-stu-id="43785-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="43785-103">Notifica al host que la tarea actual se va a suspender.</span><span class="sxs-lookup"><span data-stu-id="43785-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43785-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43785-104">Syntax</span></span>  
  
```  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43785-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43785-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="43785-106">[in] El intervalo de tiempo, en milisegundos, que el subproceso estará en suspensión.</span><span class="sxs-lookup"><span data-stu-id="43785-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="43785-107">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores de enumeración, que indica qué acción debe realizar el host si esta acción se bloquea.</span><span class="sxs-lookup"><span data-stu-id="43785-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43785-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43785-108">Return Value</span></span>  
  
|<span data-ttu-id="43785-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43785-109">HRESULT</span></span>|<span data-ttu-id="43785-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="43785-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43785-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="43785-111">S_OK</span></span>|<span data-ttu-id="43785-112">`Sleep` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="43785-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="43785-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="43785-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="43785-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="43785-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="43785-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="43785-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="43785-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="43785-116">The call timed out.</span></span>|  
|<span data-ttu-id="43785-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="43785-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="43785-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="43785-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="43785-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="43785-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="43785-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="43785-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="43785-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43785-121">E_FAIL</span></span>|<span data-ttu-id="43785-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="43785-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="43785-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="43785-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="43785-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="43785-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43785-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43785-125">Remarks</span></span>  
 <span data-ttu-id="43785-126">CLR llama normalmente `IHostTaskManager::Sleep` cuando <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> se llama desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="43785-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43785-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43785-127">Requirements</span></span>  
 <span data-ttu-id="43785-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43785-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43785-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43785-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43785-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43785-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43785-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43785-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43785-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="43785-132">See also</span></span>
- [<span data-ttu-id="43785-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43785-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="43785-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43785-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="43785-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43785-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="43785-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43785-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
