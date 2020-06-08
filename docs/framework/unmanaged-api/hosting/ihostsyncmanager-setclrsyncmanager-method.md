---
title: IHostSyncManager::SetCLRSyncManager (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
ms.openlocfilehash: 7f1832b22a1b80855f48eba6d39bff64da6fa5f9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501448"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="d3eae-102">IHostSyncManager::SetCLRSyncManager (Método)</span><span class="sxs-lookup"><span data-stu-id="d3eae-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="d3eae-103">Establece la instancia de [ICLRSyncManager](iclrsyncmanager-interface.md) que se va a asociar a la instancia actual de [IHostSyncManager](ihostsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d3eae-103">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3eae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3eae-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3eae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3eae-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="d3eae-106">de Puntero a una `ICLRSyncManager` instancia de proporcionada por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d3eae-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3eae-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d3eae-107">Return Value</span></span>  
  
|<span data-ttu-id="d3eae-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3eae-108">HRESULT</span></span>|<span data-ttu-id="d3eae-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3eae-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3eae-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3eae-110">S_OK</span></span>|<span data-ttu-id="d3eae-111">`SetCLRSyncManager`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3eae-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="d3eae-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d3eae-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3eae-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3eae-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d3eae-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d3eae-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d3eae-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d3eae-115">The call timed out.</span></span>|  
|<span data-ttu-id="d3eae-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d3eae-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d3eae-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d3eae-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d3eae-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d3eae-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d3eae-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d3eae-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d3eae-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3eae-120">E_FAIL</span></span>|<span data-ttu-id="d3eae-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d3eae-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d3eae-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d3eae-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d3eae-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d3eae-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3eae-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3eae-124">Remarks</span></span>  
 <span data-ttu-id="d3eae-125">Para facilitar la comunicación entre el host y el CLR, las interfaces de hospedaje generalmente están en parejas.</span><span class="sxs-lookup"><span data-stu-id="d3eae-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="d3eae-126">Un miembro del par se implementa mediante el host y CLR implementa el otro miembro.</span><span class="sxs-lookup"><span data-stu-id="d3eae-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="d3eae-127">Como implementación del lado host, la `IHostSyncManager` interfaz corresponde a la `ICLRSyncManager` interfaz implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="d3eae-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="d3eae-128">CLR llama `SetCLRSyncManager` a para proporcionar una `ICLRSyncManager` instancia del host que se va a asociar a la `IHostSyncManager` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="d3eae-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3eae-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3eae-129">Requirements</span></span>  
 <span data-ttu-id="d3eae-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3eae-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3eae-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d3eae-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3eae-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d3eae-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3eae-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3eae-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3eae-134">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="d3eae-134">See also</span></span>

- [<span data-ttu-id="d3eae-135">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3eae-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d3eae-136">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3eae-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
