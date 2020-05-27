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
ms.openlocfilehash: bb12547155383bb410f592018232ca6f688bab8a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841912"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="b4c66-102">IHostTaskManager::Sleep (Método)</span><span class="sxs-lookup"><span data-stu-id="b4c66-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="b4c66-103">Notifica al host que la tarea actual va a entrar en suspensión.</span><span class="sxs-lookup"><span data-stu-id="b4c66-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4c66-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4c66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4c66-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="b4c66-106">de El intervalo de tiempo, en milisegundos, que el subproceso entrará en suspensión.</span><span class="sxs-lookup"><span data-stu-id="b4c66-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="b4c66-107">de Uno de los valores de enumeración de [WAIT_OPTION](wait-option-enumeration.md) , que indica qué acción debe realizar el host si esta acción se bloquea.</span><span class="sxs-lookup"><span data-stu-id="b4c66-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4c66-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4c66-108">Return Value</span></span>  
  
|<span data-ttu-id="b4c66-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4c66-109">HRESULT</span></span>|<span data-ttu-id="b4c66-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4c66-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4c66-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4c66-111">S_OK</span></span>|<span data-ttu-id="b4c66-112">`Sleep`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4c66-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="b4c66-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4c66-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4c66-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4c66-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4c66-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4c66-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4c66-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b4c66-116">The call timed out.</span></span>|  
|<span data-ttu-id="b4c66-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4c66-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4c66-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b4c66-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4c66-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4c66-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4c66-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="b4c66-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4c66-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4c66-121">E_FAIL</span></span>|<span data-ttu-id="b4c66-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b4c66-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4c66-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b4c66-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4c66-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b4c66-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4c66-125">Notas</span><span class="sxs-lookup"><span data-stu-id="b4c66-125">Remarks</span></span>  
 <span data-ttu-id="b4c66-126">CLR normalmente llama a `IHostTaskManager::Sleep` cuando <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> se llama a desde el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4c66-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4c66-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4c66-127">Requirements</span></span>  
 <span data-ttu-id="b4c66-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4c66-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4c66-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b4c66-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4c66-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b4c66-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4c66-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4c66-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c66-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4c66-132">See also</span></span>

- [<span data-ttu-id="b4c66-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4c66-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b4c66-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4c66-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b4c66-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4c66-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b4c66-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4c66-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
