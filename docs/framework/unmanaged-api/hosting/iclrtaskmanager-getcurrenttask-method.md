---
title: ICLRTaskManager::GetCurrentTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: af855e3ba47dc329a4fb722c3e13d5f1816beba4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723284"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="e03a4-102">ICLRTaskManager::GetCurrentTask (Método)</span><span class="sxs-lookup"><span data-stu-id="e03a4-102">ICLRTaskManager::GetCurrentTask Method</span></span>

<span data-ttu-id="e03a4-103">Obtiene la instancia de [ICLRTask](iclrtask-interface.md) que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se originó la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="e03a4-103">Gets the [ICLRTask](iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e03a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e03a4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e03a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e03a4-105">Parameters</span></span>  

 `ppTask`  
 <span data-ttu-id="e03a4-106">enuncia Puntero a la dirección de una `ICLRTask` instancia de que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se originó la llamada, o null si no hay ninguna tarea en ejecución actualmente en este subproceso.</span><span class="sxs-lookup"><span data-stu-id="e03a4-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e03a4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e03a4-107">Return Value</span></span>  
  
|<span data-ttu-id="e03a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e03a4-108">HRESULT</span></span>|<span data-ttu-id="e03a4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e03a4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e03a4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e03a4-110">S_OK</span></span>|<span data-ttu-id="e03a4-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e03a4-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="e03a4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e03a4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e03a4-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e03a4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e03a4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e03a4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e03a4-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e03a4-115">The call timed out.</span></span>|  
|<span data-ttu-id="e03a4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e03a4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e03a4-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e03a4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e03a4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e03a4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e03a4-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e03a4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e03a4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e03a4-120">E_FAIL</span></span>|<span data-ttu-id="e03a4-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e03a4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e03a4-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e03a4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e03a4-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e03a4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e03a4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e03a4-124">Remarks</span></span>  

 <span data-ttu-id="e03a4-125">La `ICLRTask` instancia a la que `ppTask` apunta el parámetro representa la tarea que se está ejecutando actualmente para CLR.</span><span class="sxs-lookup"><span data-stu-id="e03a4-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="e03a4-126">La `ICLRTask` instancia de está asociada a una instancia de [IHostTask](ihosttask-interface.md) correspondiente que representa la tarea para el host.</span><span class="sxs-lookup"><span data-stu-id="e03a4-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e03a4-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e03a4-127">Requirements</span></span>  

 <span data-ttu-id="e03a4-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e03a4-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e03a4-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e03a4-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e03a4-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e03a4-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e03a4-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e03a4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e03a4-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e03a4-132">See also</span></span>

- [<span data-ttu-id="e03a4-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e03a4-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e03a4-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e03a4-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e03a4-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e03a4-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e03a4-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e03a4-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
