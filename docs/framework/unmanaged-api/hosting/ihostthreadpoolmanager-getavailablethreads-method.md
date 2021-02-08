---
description: 'Más información acerca de: IHostThreadPoolManager:: GetAvailableThreads (método)'
title: IHostThreadPoolManager::GetAvailableThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 95ecaa5757442bb384d303c1f8dafa342bd62f5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789340"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="cb7ef-103">IHostThreadPoolManager::GetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="cb7ef-103">IHostThreadPoolManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="cb7ef-104">Obtiene el número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-104">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb7ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb7ef-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb7ef-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb7ef-106">Parameters</span></span>  

 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="cb7ef-107">enuncia Puntero al número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-107">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb7ef-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cb7ef-108">Return Value</span></span>  
  
|<span data-ttu-id="cb7ef-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cb7ef-109">HRESULT</span></span>|<span data-ttu-id="cb7ef-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb7ef-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb7ef-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb7ef-111">S_OK</span></span>|<span data-ttu-id="cb7ef-112">`GetAvailableThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-112">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="cb7ef-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cb7ef-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cb7ef-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cb7ef-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cb7ef-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cb7ef-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-116">The call timed out.</span></span>|  
|<span data-ttu-id="cb7ef-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cb7ef-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cb7ef-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cb7ef-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cb7ef-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cb7ef-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cb7ef-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cb7ef-121">E_FAIL</span></span>|<span data-ttu-id="cb7ef-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cb7ef-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cb7ef-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cb7ef-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cb7ef-125">E_NOTIMPL</span></span>|<span data-ttu-id="cb7ef-126">El host no proporciona una implementación de `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="cb7ef-126">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb7ef-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb7ef-127">Remarks</span></span>  

 <span data-ttu-id="cb7ef-128">Si el host no proporciona una implementación de `GetAvailableThreads` , debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="cb7ef-128">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb7ef-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb7ef-129">Requirements</span></span>  

 <span data-ttu-id="cb7ef-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb7ef-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb7ef-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cb7ef-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb7ef-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb7ef-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb7ef-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb7ef-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7ef-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb7ef-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="cb7ef-135">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb7ef-135">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
