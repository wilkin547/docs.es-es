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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9164e64c56a8a4ae908a3d06f878b399550703f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715405"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="5e981-102">ICLRTask::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="5e981-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="5e981-103">Solicita que common language runtime (CLR) anule la tarea que actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) representa la instancia.</span><span class="sxs-lookup"><span data-stu-id="5e981-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e981-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e981-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5e981-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5e981-105">Return Value</span></span>  
  
|<span data-ttu-id="5e981-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e981-106">HRESULT</span></span>|<span data-ttu-id="5e981-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e981-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e981-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e981-108">S_OK</span></span>|<span data-ttu-id="5e981-109">`Abort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5e981-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="5e981-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e981-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e981-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5e981-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e981-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e981-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e981-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5e981-113">The call timed out.</span></span>|  
|<span data-ttu-id="5e981-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e981-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e981-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5e981-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e981-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e981-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e981-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="5e981-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e981-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e981-118">E_FAIL</span></span>|<span data-ttu-id="5e981-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="5e981-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e981-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5e981-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e981-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5e981-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e981-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e981-122">Remarks</span></span>  
 <span data-ttu-id="5e981-123">CLR genera un <xref:System.Threading.ThreadAbortException> cuando el host llama `Abort`.</span><span class="sxs-lookup"><span data-stu-id="5e981-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="5e981-124">Devuelve inmediatamente después de inicializa la información de excepción, sin esperar a que el código de usuario, por ejemplo, finalizadores o mecanismos de control de excepciones para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="5e981-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="5e981-125">Las llamadas a `Abort` , por tanto, se devuelve rápidamente.</span><span class="sxs-lookup"><span data-stu-id="5e981-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e981-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e981-126">Requirements</span></span>  
 <span data-ttu-id="5e981-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e981-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e981-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e981-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e981-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5e981-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e981-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e981-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e981-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e981-131">See also</span></span>
- [<span data-ttu-id="5e981-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e981-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5e981-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e981-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5e981-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e981-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5e981-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e981-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
