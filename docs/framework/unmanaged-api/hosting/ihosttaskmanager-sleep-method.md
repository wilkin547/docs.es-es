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
ms.openlocfilehash: 372b15a565f8a7484c1c42c387098a38f7bbf428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702061"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="7cfe9-102">IHostTaskManager::Sleep (Método)</span><span class="sxs-lookup"><span data-stu-id="7cfe9-102">IHostTaskManager::Sleep Method</span></span>

<span data-ttu-id="7cfe9-103">Notifica al host que la tarea actual va a entrar en suspensión.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cfe9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cfe9-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cfe9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7cfe9-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="7cfe9-106">de El intervalo de tiempo, en milisegundos, que el subproceso entrará en suspensión.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="7cfe9-107">de Uno de los valores de enumeración de [WAIT_OPTION](wait-option-enumeration.md) , que indica qué acción debe realizar el host si esta acción se bloquea.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cfe9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7cfe9-108">Return Value</span></span>  
  
|<span data-ttu-id="7cfe9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cfe9-109">HRESULT</span></span>|<span data-ttu-id="7cfe9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7cfe9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7cfe9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7cfe9-111">S_OK</span></span>|<span data-ttu-id="7cfe9-112">`Sleep` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="7cfe9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7cfe9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7cfe9-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7cfe9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7cfe9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7cfe9-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-116">The call timed out.</span></span>|  
|<span data-ttu-id="7cfe9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7cfe9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7cfe9-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7cfe9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7cfe9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7cfe9-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7cfe9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7cfe9-121">E_FAIL</span></span>|<span data-ttu-id="7cfe9-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7cfe9-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7cfe9-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cfe9-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7cfe9-125">Remarks</span></span>  

 <span data-ttu-id="7cfe9-126">CLR normalmente llama a `IHostTaskManager::Sleep` cuando <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> se llama a desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cfe9-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cfe9-127">Requirements</span></span>  

 <span data-ttu-id="7cfe9-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cfe9-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cfe9-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7cfe9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7cfe9-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7cfe9-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cfe9-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cfe9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cfe9-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7cfe9-132">See also</span></span>

- [<span data-ttu-id="7cfe9-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cfe9-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="7cfe9-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cfe9-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="7cfe9-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cfe9-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="7cfe9-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cfe9-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
