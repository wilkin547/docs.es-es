---
title: IHostIoCompletionManager::SetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
ms.openlocfilehash: 55727903a7f3c798e7472de6de5249de98af7ae7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804670"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="b360a-102">IHostIoCompletionManager::SetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="b360a-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="b360a-103">Establece el número máximo de subprocesos que el host asigna a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="b360a-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b360a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b360a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b360a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b360a-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="b360a-106">de Número máximo de subprocesos que se van a asignar para solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="b360a-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b360a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b360a-107">Return Value</span></span>  
  
|<span data-ttu-id="b360a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b360a-108">HRESULT</span></span>|<span data-ttu-id="b360a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b360a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b360a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b360a-110">S_OK</span></span>|<span data-ttu-id="b360a-111">`SetMaxThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b360a-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b360a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b360a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b360a-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b360a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b360a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b360a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b360a-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b360a-115">The call timed out.</span></span>|  
|<span data-ttu-id="b360a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b360a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b360a-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b360a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b360a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b360a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b360a-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="b360a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b360a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b360a-120">E_FAIL</span></span>|<span data-ttu-id="b360a-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b360a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b360a-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b360a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b360a-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b360a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b360a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b360a-124">E_NOTIMPL</span></span>|<span data-ttu-id="b360a-125">El host no proporciona una implementación de `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="b360a-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b360a-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b360a-126">Remarks</span></span>  
 <span data-ttu-id="b360a-127">`SetMaxThreads`proporciona a CLR una oportunidad para establecer el número máximo de subprocesos que están disponibles para las solicitudes de servicio en los puertos de e/s.</span><span class="sxs-lookup"><span data-stu-id="b360a-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="b360a-128">Es posible que un host necesite un control exclusivo sobre el tamaño del grupo de subprocesos, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="b360a-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b360a-129">Por esta razón, no es necesario que el host implemente `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="b360a-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="b360a-130">En este caso, un host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="b360a-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b360a-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b360a-131">Requirements</span></span>  
 <span data-ttu-id="b360a-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b360a-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b360a-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b360a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b360a-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b360a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b360a-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b360a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b360a-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b360a-136">See also</span></span>

- [<span data-ttu-id="b360a-137">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b360a-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b360a-138">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b360a-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
