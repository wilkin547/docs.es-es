---
description: 'Más información sobre: IHostIoCompletionManager:: GetMinThreads ((método)'
title: IHostIoCompletionManager::GetMinThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
ms.openlocfilehash: 73b8d8cbff3777fe6aa956f282d3da5d4ac1b5c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708526"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="f89af-103">IHostIoCompletionManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="f89af-103">IHostIoCompletionManager::GetMinThreads Method</span></span>

<span data-ttu-id="f89af-104">Obtiene el número mínimo de subprocesos que el host proporciona para procesar solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="f89af-104">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f89af-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f89af-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f89af-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f89af-106">Parameters</span></span>  

 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="f89af-107">enuncia Puntero al número mínimo de subprocesos que el host proporciona para procesar solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="f89af-107">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f89af-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f89af-108">Return Value</span></span>  
  
|<span data-ttu-id="f89af-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f89af-109">HRESULT</span></span>|<span data-ttu-id="f89af-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f89af-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f89af-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f89af-111">S_OK</span></span>|<span data-ttu-id="f89af-112">`GetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f89af-112">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="f89af-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f89af-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f89af-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f89af-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f89af-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f89af-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f89af-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f89af-116">The call timed out.</span></span>|  
|<span data-ttu-id="f89af-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f89af-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f89af-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f89af-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f89af-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f89af-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f89af-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f89af-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f89af-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f89af-121">E_FAIL</span></span>|<span data-ttu-id="f89af-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f89af-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f89af-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f89af-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f89af-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f89af-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f89af-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f89af-125">E_NOTIMPL</span></span>|<span data-ttu-id="f89af-126">El host no proporciona una implementación de `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="f89af-126">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f89af-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f89af-127">Remarks</span></span>  

 <span data-ttu-id="f89af-128">Un host podría querer tener un control exclusivo sobre el número de subprocesos asignados a las solicitudes de e/s de servicio, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="f89af-128">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="f89af-129">Por esta razón, no es necesario que el host implemente `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="f89af-129">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="f89af-130">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="f89af-130">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f89af-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f89af-131">Requirements</span></span>  

 <span data-ttu-id="f89af-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f89af-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f89af-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f89af-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f89af-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f89af-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f89af-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f89af-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89af-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="f89af-136">See also</span></span>

- [<span data-ttu-id="f89af-137">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f89af-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="f89af-138">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f89af-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
