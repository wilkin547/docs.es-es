---
description: 'Más información sobre: IHostIoCompletionManager:: GetMaxThreads (método)'
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
ms.openlocfilehash: 10c36c058f5161330842fa9d71813c4520d4655c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708541"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="86b49-103">IHostIoCompletionManager::GetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="86b49-103">IHostIoCompletionManager::GetMaxThreads Method</span></span>

<span data-ttu-id="86b49-104">Obtiene el número máximo de subprocesos que el host puede asignar a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="86b49-104">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86b49-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86b49-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86b49-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86b49-106">Parameters</span></span>  

 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="86b49-107">enuncia Puntero al número máximo de subprocesos del grupo de subprocesos que el host puede asignar a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="86b49-107">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86b49-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="86b49-108">Return Value</span></span>  
  
|<span data-ttu-id="86b49-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86b49-109">HRESULT</span></span>|<span data-ttu-id="86b49-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="86b49-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86b49-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="86b49-111">S_OK</span></span>|<span data-ttu-id="86b49-112">`GetMaxThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="86b49-112">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="86b49-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86b49-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86b49-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="86b49-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="86b49-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86b49-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86b49-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="86b49-116">The call timed out.</span></span>|  
|<span data-ttu-id="86b49-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86b49-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86b49-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="86b49-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86b49-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86b49-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86b49-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="86b49-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86b49-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86b49-121">E_FAIL</span></span>|<span data-ttu-id="86b49-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="86b49-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86b49-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="86b49-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86b49-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="86b49-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="86b49-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="86b49-125">E_NOTIMPL</span></span>|<span data-ttu-id="86b49-126">El host no proporciona una implementación de `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="86b49-126">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86b49-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86b49-127">Remarks</span></span>  

 <span data-ttu-id="86b49-128">Un host podría querer controlar de forma exclusiva el número de subprocesos que se pueden asignar para procesar solicitudes de e/s, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="86b49-128">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="86b49-129">Por esta razón, no es necesario que el host implemente `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="86b49-129">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="86b49-130">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="86b49-130">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86b49-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86b49-131">Requirements</span></span>  

 <span data-ttu-id="86b49-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86b49-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86b49-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="86b49-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86b49-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86b49-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86b49-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86b49-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b49-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="86b49-136">See also</span></span>

- [<span data-ttu-id="86b49-137">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86b49-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="86b49-138">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86b49-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
