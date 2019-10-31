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
ms.openlocfilehash: 7eedf052b6f2285799940b394d9891975230cb72
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132927"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="e3965-102">IHostTaskManager::Sleep (Método)</span><span class="sxs-lookup"><span data-stu-id="e3965-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="e3965-103">Notifica al host que la tarea actual va a entrar en suspensión.</span><span class="sxs-lookup"><span data-stu-id="e3965-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3965-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3965-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3965-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3965-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="e3965-106">de El intervalo de tiempo, en milisegundos, que el subproceso entrará en suspensión.</span><span class="sxs-lookup"><span data-stu-id="e3965-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="e3965-107">de Uno de los valores de enumeración de [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , que indica qué acción debe realizar el host si esta acción se bloquea.</span><span class="sxs-lookup"><span data-stu-id="e3965-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3965-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e3965-108">Return Value</span></span>  
  
|<span data-ttu-id="e3965-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3965-109">HRESULT</span></span>|<span data-ttu-id="e3965-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3965-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3965-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3965-111">S_OK</span></span>|<span data-ttu-id="e3965-112">`Sleep` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e3965-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="e3965-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3965-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3965-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e3965-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3965-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3965-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3965-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e3965-116">The call timed out.</span></span>|  
|<span data-ttu-id="e3965-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3965-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3965-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e3965-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3965-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3965-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3965-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e3965-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3965-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3965-121">E_FAIL</span></span>|<span data-ttu-id="e3965-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e3965-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e3965-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e3965-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3965-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e3965-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3965-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3965-125">Remarks</span></span>  
 <span data-ttu-id="e3965-126">CLR normalmente llama a `IHostTaskManager::Sleep` cuando se llama a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="e3965-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3965-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3965-127">Requirements</span></span>  
 <span data-ttu-id="e3965-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3965-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3965-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e3965-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3965-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e3965-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3965-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3965-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3965-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3965-132">See also</span></span>

- [<span data-ttu-id="e3965-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3965-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e3965-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3965-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e3965-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3965-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e3965-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3965-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
