---
description: 'Más información acerca de: IHostTaskManager:: Sleep (método)'
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
ms.openlocfilehash: fedb87c6bd4558a2aa6158299551327cb2271d51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789377"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="27b4d-103">IHostTaskManager::Sleep (Método)</span><span class="sxs-lookup"><span data-stu-id="27b4d-103">IHostTaskManager::Sleep Method</span></span>

<span data-ttu-id="27b4d-104">Notifica al host que la tarea actual va a entrar en suspensión.</span><span class="sxs-lookup"><span data-stu-id="27b4d-104">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27b4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27b4d-105">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27b4d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="27b4d-106">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="27b4d-107">de El intervalo de tiempo, en milisegundos, que el subproceso entrará en suspensión.</span><span class="sxs-lookup"><span data-stu-id="27b4d-107">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="27b4d-108">de Uno de los valores de enumeración de [WAIT_OPTION](wait-option-enumeration.md) , que indica qué acción debe realizar el host si esta acción se bloquea.</span><span class="sxs-lookup"><span data-stu-id="27b4d-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27b4d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="27b4d-109">Return Value</span></span>  
  
|<span data-ttu-id="27b4d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27b4d-110">HRESULT</span></span>|<span data-ttu-id="27b4d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="27b4d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27b4d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="27b4d-112">S_OK</span></span>|<span data-ttu-id="27b4d-113">`Sleep` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="27b4d-113">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="27b4d-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27b4d-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27b4d-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="27b4d-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27b4d-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27b4d-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27b4d-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="27b4d-117">The call timed out.</span></span>|  
|<span data-ttu-id="27b4d-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27b4d-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27b4d-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="27b4d-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27b4d-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27b4d-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27b4d-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="27b4d-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27b4d-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27b4d-122">E_FAIL</span></span>|<span data-ttu-id="27b4d-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="27b4d-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27b4d-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="27b4d-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27b4d-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="27b4d-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27b4d-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="27b4d-126">Remarks</span></span>  

 <span data-ttu-id="27b4d-127">CLR normalmente llama a `IHostTaskManager::Sleep` cuando <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> se llama a desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="27b4d-127">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27b4d-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27b4d-128">Requirements</span></span>  

 <span data-ttu-id="27b4d-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27b4d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27b4d-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="27b4d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27b4d-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27b4d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27b4d-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27b4d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b4d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="27b4d-133">See also</span></span>

- [<span data-ttu-id="27b4d-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27b4d-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="27b4d-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27b4d-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="27b4d-136">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27b4d-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="27b4d-137">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27b4d-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
