---
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
ms.openlocfilehash: 026d4c14abed030b80e8e1b3f8363fbd59ac05e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124920"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="98b33-102">ICLRTask::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="98b33-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="98b33-103">Solicita que el Common Language Runtime (CLR) anule la tarea que la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) actual representa.</span><span class="sxs-lookup"><span data-stu-id="98b33-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98b33-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98b33-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="98b33-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98b33-105">Return Value</span></span>  
  
|<span data-ttu-id="98b33-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98b33-106">HRESULT</span></span>|<span data-ttu-id="98b33-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="98b33-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98b33-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="98b33-108">S_OK</span></span>|<span data-ttu-id="98b33-109">`Abort` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="98b33-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="98b33-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98b33-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98b33-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="98b33-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98b33-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="98b33-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="98b33-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="98b33-113">The call timed out.</span></span>|  
|<span data-ttu-id="98b33-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="98b33-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="98b33-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="98b33-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="98b33-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="98b33-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="98b33-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="98b33-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="98b33-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98b33-118">E_FAIL</span></span>|<span data-ttu-id="98b33-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="98b33-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98b33-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="98b33-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98b33-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="98b33-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98b33-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98b33-122">Remarks</span></span>  
 <span data-ttu-id="98b33-123">CLR genera una <xref:System.Threading.ThreadAbortException> cuando el host llama a `Abort`.</span><span class="sxs-lookup"><span data-stu-id="98b33-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="98b33-124">Vuelve inmediatamente después de inicializar la información de excepción, sin esperar a que se ejecute el código de usuario, como finalizadores o mecanismos de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="98b33-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="98b33-125">De este modo, las llamadas a `Abort` devuelven rápidamente.</span><span class="sxs-lookup"><span data-stu-id="98b33-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98b33-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98b33-126">Requirements</span></span>  
 <span data-ttu-id="98b33-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98b33-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98b33-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="98b33-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98b33-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="98b33-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98b33-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98b33-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b33-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="98b33-131">See also</span></span>

- [<span data-ttu-id="98b33-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98b33-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="98b33-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98b33-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="98b33-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98b33-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="98b33-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98b33-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
