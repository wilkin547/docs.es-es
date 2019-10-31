---
title: IHostIoCompletionManager::GetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
ms.openlocfilehash: d35fd91f2a28c392176a6dd87bd21baa964ee9a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133815"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="ef245-102">IHostIoCompletionManager::GetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="ef245-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="ef245-103">Obtiene el número máximo de subprocesos que el host puede asignar a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="ef245-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef245-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef245-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef245-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef245-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="ef245-106">enuncia Puntero al número máximo de subprocesos del grupo de subprocesos que el host puede asignar a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="ef245-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef245-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ef245-107">Return Value</span></span>  
  
|<span data-ttu-id="ef245-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef245-108">HRESULT</span></span>|<span data-ttu-id="ef245-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef245-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef245-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef245-110">S_OK</span></span>|<span data-ttu-id="ef245-111">`GetMaxThreads` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ef245-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ef245-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef245-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ef245-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ef245-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ef245-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ef245-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ef245-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ef245-115">The call timed out.</span></span>|  
|<span data-ttu-id="ef245-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ef245-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ef245-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ef245-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ef245-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ef245-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ef245-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ef245-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ef245-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef245-120">E_FAIL</span></span>|<span data-ttu-id="ef245-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ef245-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ef245-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ef245-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ef245-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ef245-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ef245-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ef245-124">E_NOTIMPL</span></span>|<span data-ttu-id="ef245-125">El host no proporciona una implementación de `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="ef245-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef245-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef245-126">Remarks</span></span>  
 <span data-ttu-id="ef245-127">Un host podría querer controlar de forma exclusiva el número de subprocesos que se pueden asignar para procesar solicitudes de e/s, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="ef245-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="ef245-128">Por esta razón, no es necesario que el host implemente `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="ef245-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="ef245-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="ef245-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef245-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef245-130">Requirements</span></span>  
 <span data-ttu-id="ef245-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef245-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef245-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ef245-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef245-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ef245-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef245-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef245-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef245-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef245-135">See also</span></span>

- [<span data-ttu-id="ef245-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef245-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ef245-137">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef245-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
