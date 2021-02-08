---
description: 'Más información acerca de: ICLRTask:: ABORT (método)'
title: ICLRTask::Abort (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
ms.openlocfilehash: ddb761ac50d7401180355236aa8fdc22cca1c580
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785017"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="433ec-103">ICLRTask::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="433ec-103">ICLRTask::Abort Method</span></span>

<span data-ttu-id="433ec-104">Solicita que el Common Language Runtime (CLR) anule la tarea que la instancia de [ICLRTask](iclrtask-interface.md) actual representa.</span><span class="sxs-lookup"><span data-stu-id="433ec-104">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="433ec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="433ec-105">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="433ec-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="433ec-106">Return Value</span></span>  
  
|<span data-ttu-id="433ec-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="433ec-107">HRESULT</span></span>|<span data-ttu-id="433ec-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="433ec-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="433ec-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="433ec-109">S_OK</span></span>|<span data-ttu-id="433ec-110">`Abort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="433ec-110">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="433ec-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="433ec-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="433ec-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="433ec-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="433ec-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="433ec-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="433ec-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="433ec-114">The call timed out.</span></span>|  
|<span data-ttu-id="433ec-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="433ec-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="433ec-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="433ec-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="433ec-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="433ec-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="433ec-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="433ec-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="433ec-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="433ec-119">E_FAIL</span></span>|<span data-ttu-id="433ec-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="433ec-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="433ec-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="433ec-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="433ec-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="433ec-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="433ec-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="433ec-123">Remarks</span></span>  

 <span data-ttu-id="433ec-124">CLR genera una <xref:System.Threading.ThreadAbortException> cuando el host llama a `Abort` .</span><span class="sxs-lookup"><span data-stu-id="433ec-124">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="433ec-125">Vuelve inmediatamente después de inicializar la información de excepción, sin esperar a que se ejecute el código de usuario, como finalizadores o mecanismos de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="433ec-125">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="433ec-126">De `Abort` este modo, las llamadas a devuelven rápidamente.</span><span class="sxs-lookup"><span data-stu-id="433ec-126">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="433ec-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="433ec-127">Requirements</span></span>  

 <span data-ttu-id="433ec-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="433ec-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="433ec-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="433ec-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="433ec-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="433ec-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="433ec-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="433ec-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="433ec-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="433ec-132">See also</span></span>

- [<span data-ttu-id="433ec-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="433ec-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="433ec-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="433ec-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="433ec-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="433ec-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="433ec-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="433ec-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
