---
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
ms.openlocfilehash: d321ce08edf4780fc5f26ac627849b9129c2f283
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673233"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="b7712-102">IHostIoCompletionManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="b7712-102">IHostIoCompletionManager::GetMinThreads Method</span></span>

<span data-ttu-id="b7712-103">Obtiene el número mínimo de subprocesos que el host proporciona para procesar solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="b7712-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7712-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7712-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7712-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7712-105">Parameters</span></span>  

 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="b7712-106">enuncia Puntero al número mínimo de subprocesos que el host proporciona para procesar solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="b7712-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7712-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7712-107">Return Value</span></span>  
  
|<span data-ttu-id="b7712-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7712-108">HRESULT</span></span>|<span data-ttu-id="b7712-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7712-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7712-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7712-110">S_OK</span></span>|<span data-ttu-id="b7712-111">`GetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b7712-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b7712-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b7712-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b7712-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b7712-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b7712-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b7712-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b7712-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b7712-115">The call timed out.</span></span>|  
|<span data-ttu-id="b7712-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b7712-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b7712-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b7712-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b7712-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b7712-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b7712-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="b7712-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b7712-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7712-120">E_FAIL</span></span>|<span data-ttu-id="b7712-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b7712-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b7712-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b7712-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b7712-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b7712-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b7712-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b7712-124">E_NOTIMPL</span></span>|<span data-ttu-id="b7712-125">El host no proporciona una implementación de `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="b7712-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7712-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7712-126">Remarks</span></span>  

 <span data-ttu-id="b7712-127">Un host podría querer tener un control exclusivo sobre el número de subprocesos asignados a las solicitudes de e/s de servicio, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="b7712-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b7712-128">Por esta razón, no es necesario que el host implemente `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="b7712-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="b7712-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="b7712-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7712-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7712-130">Requirements</span></span>  

 <span data-ttu-id="b7712-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7712-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7712-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b7712-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7712-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7712-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7712-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7712-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7712-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7712-135">See also</span></span>

- [<span data-ttu-id="b7712-136">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7712-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b7712-137">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7712-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
