---
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
ms.openlocfilehash: cc03960c2d45a6cf8aed58eaf048a0531decb08f
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842340"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="a5976-102">IHostThreadPoolManager::GetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="a5976-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="a5976-103">Obtiene el número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5976-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5976-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5976-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5976-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5976-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="a5976-106">enuncia Puntero al número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5976-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5976-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a5976-107">Return Value</span></span>  
  
|<span data-ttu-id="a5976-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5976-108">HRESULT</span></span>|<span data-ttu-id="a5976-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5976-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5976-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5976-110">S_OK</span></span>|<span data-ttu-id="a5976-111">`GetAvailableThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5976-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a5976-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a5976-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a5976-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5976-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a5976-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a5976-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a5976-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a5976-115">The call timed out.</span></span>|  
|<span data-ttu-id="a5976-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a5976-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a5976-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a5976-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a5976-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a5976-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a5976-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a5976-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a5976-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a5976-120">E_FAIL</span></span>|<span data-ttu-id="a5976-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a5976-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a5976-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a5976-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a5976-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a5976-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a5976-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a5976-124">E_NOTIMPL</span></span>|<span data-ttu-id="a5976-125">El host no proporciona una implementación de `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="a5976-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5976-126">Notas</span><span class="sxs-lookup"><span data-stu-id="a5976-126">Remarks</span></span>  
 <span data-ttu-id="a5976-127">Si el host no proporciona una implementación de `GetAvailableThreads` , debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a5976-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5976-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5976-128">Requirements</span></span>  
 <span data-ttu-id="a5976-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5976-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5976-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a5976-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5976-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a5976-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5976-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5976-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5976-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5976-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a5976-134">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5976-134">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
