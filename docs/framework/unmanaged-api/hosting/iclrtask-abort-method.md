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
ms.openlocfilehash: 76f216b12bccc950a34e2b23404ac305de519f4a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762479"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="0936b-102">ICLRTask::Abort (Método)</span><span class="sxs-lookup"><span data-stu-id="0936b-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="0936b-103">Solicita que el Common Language Runtime (CLR) anule la tarea que la instancia de [ICLRTask](iclrtask-interface.md) actual representa.</span><span class="sxs-lookup"><span data-stu-id="0936b-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0936b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0936b-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0936b-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0936b-105">Return Value</span></span>  
  
|<span data-ttu-id="0936b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0936b-106">HRESULT</span></span>|<span data-ttu-id="0936b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0936b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0936b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0936b-108">S_OK</span></span>|<span data-ttu-id="0936b-109">`Abort`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0936b-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="0936b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0936b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0936b-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0936b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0936b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0936b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0936b-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0936b-113">The call timed out.</span></span>|  
|<span data-ttu-id="0936b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0936b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0936b-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0936b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0936b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0936b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0936b-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0936b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0936b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0936b-118">E_FAIL</span></span>|<span data-ttu-id="0936b-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0936b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0936b-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0936b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0936b-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0936b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0936b-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0936b-122">Remarks</span></span>  
 <span data-ttu-id="0936b-123">CLR genera una <xref:System.Threading.ThreadAbortException> cuando el host llama a `Abort` .</span><span class="sxs-lookup"><span data-stu-id="0936b-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="0936b-124">Vuelve inmediatamente después de inicializar la información de excepción, sin esperar a que se ejecute el código de usuario, como finalizadores o mecanismos de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0936b-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="0936b-125">De `Abort` este modo, las llamadas a devuelven rápidamente.</span><span class="sxs-lookup"><span data-stu-id="0936b-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0936b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0936b-126">Requirements</span></span>  
 <span data-ttu-id="0936b-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0936b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0936b-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0936b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0936b-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0936b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0936b-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0936b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0936b-131">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0936b-131">See also</span></span>

- [<span data-ttu-id="0936b-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0936b-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0936b-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0936b-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0936b-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0936b-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0936b-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0936b-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
