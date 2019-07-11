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
ms.openlocfilehash: 0e25f2e49ab25d2df827fdd59526b13976d21219
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756567"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="a2473-102">IHostTaskManager::Sleep (Método)</span><span class="sxs-lookup"><span data-stu-id="a2473-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="a2473-103">Notifica al host que la tarea actual se va a suspender.</span><span class="sxs-lookup"><span data-stu-id="a2473-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2473-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2473-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2473-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2473-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="a2473-106">[in] El intervalo de tiempo, en milisegundos, que el subproceso estará en suspensión.</span><span class="sxs-lookup"><span data-stu-id="a2473-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="a2473-107">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores de enumeración, que indica qué acción debe realizar el host si esta acción se bloquea.</span><span class="sxs-lookup"><span data-stu-id="a2473-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2473-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a2473-108">Return Value</span></span>  
  
|<span data-ttu-id="a2473-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2473-109">HRESULT</span></span>|<span data-ttu-id="a2473-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a2473-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2473-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2473-111">S_OK</span></span>|<span data-ttu-id="a2473-112">`Sleep` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a2473-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="a2473-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a2473-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a2473-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a2473-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a2473-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a2473-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a2473-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a2473-116">The call timed out.</span></span>|  
|<span data-ttu-id="a2473-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a2473-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a2473-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a2473-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a2473-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a2473-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a2473-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a2473-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a2473-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a2473-121">E_FAIL</span></span>|<span data-ttu-id="a2473-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a2473-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a2473-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a2473-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a2473-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a2473-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2473-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2473-125">Remarks</span></span>  
 <span data-ttu-id="a2473-126">CLR llama normalmente `IHostTaskManager::Sleep` cuando <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> se llama desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="a2473-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2473-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2473-127">Requirements</span></span>  
 <span data-ttu-id="a2473-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2473-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2473-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2473-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2473-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2473-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2473-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2473-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2473-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2473-132">See also</span></span>

- [<span data-ttu-id="a2473-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2473-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a2473-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2473-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a2473-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2473-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a2473-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2473-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
