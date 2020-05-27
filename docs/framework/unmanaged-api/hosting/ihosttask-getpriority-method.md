---
title: IHostTask::GetPriority (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: e41fcf2f03b024c1b4ae0032c0ff025d6e2aa1c3
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842509"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="243b2-102">IHostTask::GetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="243b2-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="243b2-103">Obtiene el nivel de prioridad del subproceso de la tarea representada por la instancia de [IHostTask](ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="243b2-103">Gets the thread priority level of the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="243b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="243b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="243b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="243b2-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="243b2-106">enuncia Un puntero a un entero que indica el nivel de prioridad del subproceso de la tarea representada por la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="243b2-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="243b2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="243b2-107">Return Value</span></span>  
  
|<span data-ttu-id="243b2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="243b2-108">HRESULT</span></span>|<span data-ttu-id="243b2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="243b2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="243b2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="243b2-110">S_OK</span></span>|<span data-ttu-id="243b2-111">`GetPriority`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="243b2-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="243b2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="243b2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="243b2-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="243b2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="243b2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="243b2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="243b2-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="243b2-115">The call timed out.</span></span>|  
|<span data-ttu-id="243b2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="243b2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="243b2-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="243b2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="243b2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="243b2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="243b2-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="243b2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="243b2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="243b2-120">E_FAIL</span></span>|<span data-ttu-id="243b2-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="243b2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="243b2-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="243b2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="243b2-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="243b2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="243b2-124">Notas</span><span class="sxs-lookup"><span data-stu-id="243b2-124">Remarks</span></span>  
 <span data-ttu-id="243b2-125">La función de Win32 define los valores de nivel de prioridad del subproceso `SetThreadPriority` .</span><span class="sxs-lookup"><span data-stu-id="243b2-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="243b2-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="243b2-126">Requirements</span></span>  
 <span data-ttu-id="243b2-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="243b2-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="243b2-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="243b2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="243b2-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="243b2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="243b2-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="243b2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="243b2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="243b2-131">See also</span></span>

- [<span data-ttu-id="243b2-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="243b2-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="243b2-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="243b2-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="243b2-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="243b2-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="243b2-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="243b2-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
