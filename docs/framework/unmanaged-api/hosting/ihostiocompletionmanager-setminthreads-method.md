---
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
ms.openlocfilehash: 64ea9fdd477ec005b089f451101b742278ab4266
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672414"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="ccfbf-102">IHostIoCompletionManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="ccfbf-102">IHostIoCompletionManager::SetMinThreads Method</span></span>

<span data-ttu-id="ccfbf-103">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccfbf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccfbf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccfbf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccfbf-105">Parameters</span></span>  

 `dwMinIoCompletionThreads`  
 <span data-ttu-id="ccfbf-106">de Número mínimo de subprocesos de finalización de e/s que debe crear el host.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccfbf-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ccfbf-107">Return Value</span></span>  
  
|<span data-ttu-id="ccfbf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccfbf-108">HRESULT</span></span>|<span data-ttu-id="ccfbf-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccfbf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccfbf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccfbf-110">S_OK</span></span>|<span data-ttu-id="ccfbf-111">`SetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ccfbf-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ccfbf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ccfbf-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ccfbf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ccfbf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ccfbf-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-115">The call timed out.</span></span>|  
|<span data-ttu-id="ccfbf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ccfbf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ccfbf-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ccfbf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ccfbf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ccfbf-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ccfbf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccfbf-120">E_FAIL</span></span>|<span data-ttu-id="ccfbf-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ccfbf-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ccfbf-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ccfbf-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ccfbf-124">E_NOTIMPL</span></span>|<span data-ttu-id="ccfbf-125">El host no proporciona una implementación de `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="ccfbf-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccfbf-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccfbf-126">Remarks</span></span>  

 <span data-ttu-id="ccfbf-127">Un host podría querer controlar de forma exclusiva el número de subprocesos que se pueden asignar para procesar solicitudes de e/s, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="ccfbf-128">Por esta razón, no es necesario que el host implemente `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="ccfbf-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="ccfbf-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="ccfbf-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccfbf-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccfbf-130">Requirements</span></span>  

 <span data-ttu-id="ccfbf-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccfbf-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccfbf-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ccfbf-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccfbf-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccfbf-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccfbf-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccfbf-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfbf-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ccfbf-135">See also</span></span>

- [<span data-ttu-id="ccfbf-136">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccfbf-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ccfbf-137">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="ccfbf-137">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="ccfbf-138">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccfbf-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
