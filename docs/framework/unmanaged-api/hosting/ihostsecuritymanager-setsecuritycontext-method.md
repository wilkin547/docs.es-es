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
ms.openlocfilehash: dadacaea2b8741afc7b8c51404e2604dc759a629
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680383"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="a3f8b-102">IHostSecurityManager::SetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="a3f8b-102">IHostSecurityManager::SetSecurityContext Method</span></span>

<span data-ttu-id="a3f8b-103">Establece el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3f8b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3f8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3f8b-105">Parameters</span></span>  

 `eContextType`  
 <span data-ttu-id="a3f8b-106">de Uno de los valores de [econtexttype (](econtexttype-enumeration.md) , que indica qué tipo de contexto coloca el Common Language Runtime (CLR) en el host.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="a3f8b-107">enuncia Puntero a la dirección de un nuevo objeto [IHostSecurityContext](ihostsecuritycontext-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a3f8b-107">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3f8b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3f8b-108">Return Value</span></span>  
  
|<span data-ttu-id="a3f8b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3f8b-109">HRESULT</span></span>|<span data-ttu-id="a3f8b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3f8b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3f8b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3f8b-111">S_OK</span></span>|<span data-ttu-id="a3f8b-112">`SetSecurityContext` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="a3f8b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3f8b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3f8b-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3f8b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3f8b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3f8b-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-116">The call timed out.</span></span>|  
|<span data-ttu-id="a3f8b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3f8b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3f8b-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3f8b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3f8b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3f8b-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3f8b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3f8b-121">E_FAIL</span></span>|<span data-ttu-id="a3f8b-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3f8b-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3f8b-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3f8b-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3f8b-125">Remarks</span></span>  

 <span data-ttu-id="a3f8b-126">CLR llama a `SetSecurityContext` en varios escenarios.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="a3f8b-127">Antes de ejecutar constructores y finalizadores de clases y módulos, CLR llama `SetSecurityContext` a para proteger el host frente a errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="a3f8b-128">A continuación, restablece el contexto de seguridad a su estado original después de la ejecución del constructor o finalizador, mediante otra llamada a `SetSecurityContext` .</span><span class="sxs-lookup"><span data-stu-id="a3f8b-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="a3f8b-129">Se produce un patrón similar con la finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="a3f8b-130">Si el host implementa [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), CLR llama a `SetSecurityContext` después de que el host llame a [ICLRIoCompletionManager:: alcomplete](iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="a3f8b-130">If the host implements [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="a3f8b-131">En los puntos asincrónicos de los subprocesos de trabajo, CLR llama a `SetSecurityContext` dentro <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o dentro de [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), dependiendo de si el host o CLR está implementando el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a3f8b-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f8b-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3f8b-132">Requirements</span></span>  

 <span data-ttu-id="a3f8b-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f8b-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f8b-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a3f8b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3f8b-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3f8b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3f8b-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f8b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f8b-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3f8b-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="a3f8b-138">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a3f8b-138">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="a3f8b-139">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f8b-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="a3f8b-140">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f8b-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="a3f8b-141">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f8b-141">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="a3f8b-142">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f8b-142">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="a3f8b-143">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f8b-143">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
