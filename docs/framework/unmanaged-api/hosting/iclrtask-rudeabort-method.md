---
title: ICLRTask::RudeAbort (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: aacf9de36dc39b63ed36b672e31f40704413d608
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176336"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="82158-102">ICLRTask::RudeAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="82158-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="82158-103">Indica a Common Language Runtime (CLR) que anule la tarea representada por la instancia actual de la [interfaz ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) de forma inmediata e incondicional.</span><span class="sxs-lookup"><span data-stu-id="82158-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82158-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82158-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="82158-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="82158-105">Return Value</span></span>  
  
|<span data-ttu-id="82158-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82158-106">HRESULT</span></span>|<span data-ttu-id="82158-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="82158-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82158-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="82158-108">S_OK</span></span>|<span data-ttu-id="82158-109">`RudeAbort`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="82158-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="82158-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82158-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82158-111">El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="82158-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82158-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82158-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82158-113">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="82158-113">The call timed out.</span></span>|  
|<span data-ttu-id="82158-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82158-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82158-115">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="82158-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82158-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82158-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82158-117">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="82158-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82158-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82158-118">E_FAIL</span></span>|<span data-ttu-id="82158-119">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="82158-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82158-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="82158-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82158-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="82158-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82158-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="82158-122">Remarks</span></span>  
 <span data-ttu-id="82158-123">Un host `RudeAbort` llama para anular una tarea inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="82158-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="82158-124">No se garantiza que se ejecuten los finalizadores y las rutinas de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="82158-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82158-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82158-125">Requirements</span></span>  
 <span data-ttu-id="82158-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82158-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82158-127">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="82158-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82158-128">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82158-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82158-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82158-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82158-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82158-130">See also</span></span>

- [<span data-ttu-id="82158-131">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82158-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="82158-132">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82158-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="82158-133">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82158-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="82158-134">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82158-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
