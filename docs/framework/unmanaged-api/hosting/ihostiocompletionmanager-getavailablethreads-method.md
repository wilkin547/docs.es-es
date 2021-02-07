---
description: 'Más información sobre: IHostIoCompletionManager:: GetAvailableThreads (método)'
title: IHostIoCompletionManager::GetAvailableThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
ms.openlocfilehash: d50f79716f72b902102a2a97a0bce5dfe645334f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708564"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="94af2-103">IHostIoCompletionManager::GetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="94af2-103">IHostIoCompletionManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="94af2-104">Obtiene el número de subprocesos de finalización de e/s, del número total de subprocesos administrados por el host, que no están atendiendo actualmente solicitudes.</span><span class="sxs-lookup"><span data-stu-id="94af2-104">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94af2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94af2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94af2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94af2-106">Parameters</span></span>  

 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="94af2-107">enuncia Puntero al número de subprocesos de finalización de e/s administrados por el host que están actualmente disponibles para las solicitudes de servicio.</span><span class="sxs-lookup"><span data-stu-id="94af2-107">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94af2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="94af2-108">Return Value</span></span>  
  
|<span data-ttu-id="94af2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94af2-109">HRESULT</span></span>|<span data-ttu-id="94af2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="94af2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94af2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="94af2-111">S_OK</span></span>|<span data-ttu-id="94af2-112">`GetAvailableThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="94af2-112">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="94af2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94af2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94af2-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="94af2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94af2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94af2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94af2-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="94af2-116">The call timed out.</span></span>|  
|<span data-ttu-id="94af2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94af2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94af2-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="94af2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94af2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94af2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94af2-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="94af2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94af2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94af2-121">E_FAIL</span></span>|<span data-ttu-id="94af2-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="94af2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94af2-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="94af2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94af2-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="94af2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="94af2-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="94af2-125">E_NOTIMPL</span></span>|<span data-ttu-id="94af2-126">El host no proporciona una implementación de `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="94af2-126">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94af2-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="94af2-127">Remarks</span></span>  

 <span data-ttu-id="94af2-128">Un host podría querer tener un control exclusivo sobre el tamaño del grupo de subprocesos de finalización de e/s, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="94af2-128">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="94af2-129">Por lo tanto, no es necesario que el host implemente `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="94af2-129">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="94af2-130">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="94af2-130">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94af2-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94af2-131">Requirements</span></span>  

 <span data-ttu-id="94af2-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94af2-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94af2-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94af2-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94af2-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94af2-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94af2-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94af2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94af2-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="94af2-136">See also</span></span>

- [<span data-ttu-id="94af2-137">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94af2-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="94af2-138">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94af2-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
