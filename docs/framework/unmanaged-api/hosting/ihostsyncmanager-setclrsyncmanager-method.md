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
ms.openlocfilehash: 9c08a790d4dad748e5d09271bd870add22255b4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132620"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="f7a0e-102">IHostSyncManager::SetCLRSyncManager (Método)</span><span class="sxs-lookup"><span data-stu-id="f7a0e-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="f7a0e-103">Establece la instancia de [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) que se va a asociar a la instancia actual de [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f7a0e-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7a0e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7a0e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7a0e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7a0e-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="f7a0e-106">de Puntero a una instancia de `ICLRSyncManager` proporcionada por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f7a0e-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7a0e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f7a0e-107">Return Value</span></span>  
  
|<span data-ttu-id="f7a0e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7a0e-108">HRESULT</span></span>|<span data-ttu-id="f7a0e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7a0e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7a0e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7a0e-110">S_OK</span></span>|<span data-ttu-id="f7a0e-111">`SetCLRSyncManager` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="f7a0e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f7a0e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f7a0e-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f7a0e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f7a0e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f7a0e-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-115">The call timed out.</span></span>|  
|<span data-ttu-id="f7a0e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f7a0e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f7a0e-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f7a0e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f7a0e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f7a0e-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f7a0e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7a0e-120">E_FAIL</span></span>|<span data-ttu-id="f7a0e-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f7a0e-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f7a0e-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7a0e-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7a0e-124">Remarks</span></span>  
 <span data-ttu-id="f7a0e-125">Para facilitar la comunicación entre el host y el CLR, las interfaces de hospedaje generalmente están en parejas.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="f7a0e-126">Un miembro del par se implementa mediante el host y CLR implementa el otro miembro.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="f7a0e-127">Como implementación del lado host, la interfaz `IHostSyncManager` corresponde a la interfaz `ICLRSyncManager` implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="f7a0e-128">CLR llama a `SetCLRSyncManager` para proporcionar una instancia de `ICLRSyncManager` para el host que se va a asociar a la instancia de `IHostSyncManager` actual.</span><span class="sxs-lookup"><span data-stu-id="f7a0e-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7a0e-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7a0e-129">Requirements</span></span>  
 <span data-ttu-id="f7a0e-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7a0e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7a0e-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f7a0e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7a0e-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f7a0e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7a0e-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7a0e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a0e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7a0e-134">See also</span></span>

- [<span data-ttu-id="f7a0e-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7a0e-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="f7a0e-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7a0e-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
