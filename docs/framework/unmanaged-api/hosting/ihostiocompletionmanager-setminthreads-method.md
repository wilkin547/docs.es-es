---
description: 'Más información sobre: IHostIoCompletionManager:: SetMinThreads ((método)'
title: IHostIoCompletionManager::SetMinThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
ms.openlocfilehash: aade5ebb9e318d51296e52e7cf1c31c6ea9e4f6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708247"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="3f56f-103">IHostIoCompletionManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="3f56f-103">IHostIoCompletionManager::SetMinThreads Method</span></span>

<span data-ttu-id="3f56f-104">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="3f56f-104">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f56f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f56f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f56f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f56f-106">Parameters</span></span>  

 `dwMinIoCompletionThreads`  
 <span data-ttu-id="3f56f-107">de Número mínimo de subprocesos de finalización de e/s que debe crear el host.</span><span class="sxs-lookup"><span data-stu-id="3f56f-107">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f56f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f56f-108">Return Value</span></span>  
  
|<span data-ttu-id="3f56f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f56f-109">HRESULT</span></span>|<span data-ttu-id="3f56f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f56f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f56f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f56f-111">S_OK</span></span>|<span data-ttu-id="3f56f-112">`SetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3f56f-112">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="3f56f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3f56f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f56f-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3f56f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f56f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f56f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f56f-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3f56f-116">The call timed out.</span></span>|  
|<span data-ttu-id="3f56f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f56f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f56f-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3f56f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f56f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f56f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f56f-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3f56f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3f56f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f56f-121">E_FAIL</span></span>|<span data-ttu-id="3f56f-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3f56f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f56f-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3f56f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f56f-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3f56f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3f56f-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3f56f-125">E_NOTIMPL</span></span>|<span data-ttu-id="3f56f-126">El host no proporciona una implementación de `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="3f56f-126">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f56f-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3f56f-127">Remarks</span></span>  

 <span data-ttu-id="3f56f-128">Un host podría querer controlar de forma exclusiva el número de subprocesos que se pueden asignar para procesar solicitudes de e/s, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="3f56f-128">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="3f56f-129">Por esta razón, no es necesario que el host implemente `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="3f56f-129">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="3f56f-130">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="3f56f-130">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f56f-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f56f-131">Requirements</span></span>  

 <span data-ttu-id="3f56f-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f56f-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f56f-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3f56f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f56f-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f56f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f56f-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f56f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f56f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f56f-136">See also</span></span>

- [<span data-ttu-id="3f56f-137">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f56f-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="3f56f-138">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="3f56f-138">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="3f56f-139">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f56f-139">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
