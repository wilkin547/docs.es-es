---
title: IHostThreadPoolManager::GetMinThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
ms.openlocfilehash: a05cfb43b5b4a328d22c4df04049a7fa156ca080
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841937"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="c5a50-102">IHostThreadPoolManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="c5a50-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="c5a50-103">Obtiene el número mínimo de subprocesos inactivos que el host mantiene en el grupo de subprocesos en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="c5a50-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5a50-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5a50-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5a50-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="c5a50-106">enuncia Puntero al número mínimo de subprocesos de trabajo inactivos que el host mantiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="c5a50-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5a50-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c5a50-107">Return Value</span></span>  
  
|<span data-ttu-id="c5a50-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5a50-108">HRESULT</span></span>|<span data-ttu-id="c5a50-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5a50-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5a50-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5a50-110">S_OK</span></span>|<span data-ttu-id="c5a50-111">`GetMinThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c5a50-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c5a50-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5a50-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5a50-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c5a50-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5a50-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5a50-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5a50-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c5a50-115">The call timed out.</span></span>|  
|<span data-ttu-id="c5a50-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5a50-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5a50-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c5a50-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5a50-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5a50-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5a50-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c5a50-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5a50-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5a50-120">E_FAIL</span></span>|<span data-ttu-id="c5a50-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c5a50-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5a50-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c5a50-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5a50-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c5a50-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c5a50-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c5a50-124">E_NOTIMPL</span></span>|<span data-ttu-id="c5a50-125">El host no proporciona una implementación de `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="c5a50-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5a50-126">Notas</span><span class="sxs-lookup"><span data-stu-id="c5a50-126">Remarks</span></span>  
 <span data-ttu-id="c5a50-127">No es necesario que el host proporcione una implementación de `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="c5a50-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="c5a50-128">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c5a50-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5a50-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5a50-129">Requirements</span></span>  
 <span data-ttu-id="c5a50-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5a50-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5a50-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c5a50-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5a50-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c5a50-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5a50-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5a50-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a50-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5a50-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="c5a50-135">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="c5a50-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="c5a50-136">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="c5a50-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="c5a50-137">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5a50-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
