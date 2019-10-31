---
title: IHostSecurityManager::SetSecurityContext (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: 676a1d50202333203c13fcf916dbb14a6d91fb8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121445"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="5c415-102">IHostSecurityManager::SetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="5c415-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="5c415-103">Establece el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="5c415-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c415-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c415-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c415-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c415-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="5c415-106">de Uno de los valores de [econtexttype (](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) , que indica qué tipo de contexto coloca el Common Language Runtime (CLR) en el host.</span><span class="sxs-lookup"><span data-stu-id="5c415-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="5c415-107">enuncia Puntero a la dirección de un nuevo objeto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5c415-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c415-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5c415-108">Return Value</span></span>  
  
|<span data-ttu-id="5c415-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c415-109">HRESULT</span></span>|<span data-ttu-id="5c415-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c415-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c415-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c415-111">S_OK</span></span>|<span data-ttu-id="5c415-112">`SetSecurityContext` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5c415-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="5c415-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5c415-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5c415-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5c415-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5c415-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5c415-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5c415-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c415-116">The call timed out.</span></span>|  
|<span data-ttu-id="5c415-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5c415-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5c415-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5c415-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5c415-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5c415-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5c415-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5c415-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5c415-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c415-121">E_FAIL</span></span>|<span data-ttu-id="5c415-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5c415-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5c415-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5c415-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5c415-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5c415-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c415-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c415-125">Remarks</span></span>  
 <span data-ttu-id="5c415-126">CLR llama a `SetSecurityContext` en varios escenarios.</span><span class="sxs-lookup"><span data-stu-id="5c415-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="5c415-127">Antes de ejecutar constructores y finalizadores de clases y módulos, CLR llama a `SetSecurityContext` para proteger el host frente a errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5c415-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="5c415-128">A continuación, restablece el contexto de seguridad a su estado original después de la ejecución del constructor o finalizador mediante otra llamada a `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="5c415-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="5c415-129">Se produce un patrón similar con la finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="5c415-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="5c415-130">Si el host implementa [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR llama a `SetSecurityContext` después de que el host llame a [ICLRIoCompletionManager:: alcomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="5c415-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="5c415-131">En los puntos asincrónicos de los subprocesos de trabajo, CLR llama a `SetSecurityContext` dentro de <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o en [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), dependiendo de si el host o CLR está implementando el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5c415-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c415-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c415-132">Requirements</span></span>  
 <span data-ttu-id="5c415-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c415-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c415-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5c415-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c415-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c415-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c415-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c415-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c415-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c415-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="5c415-138">EContextType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="5c415-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="5c415-139">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c415-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="5c415-140">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c415-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="5c415-141">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c415-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="5c415-142">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c415-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="5c415-143">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c415-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
