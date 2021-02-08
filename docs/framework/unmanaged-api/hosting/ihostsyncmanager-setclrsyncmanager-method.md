---
description: 'Más información acerca de: IHostSyncManager:: Setclrsyncmanager ((método)'
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
ms.openlocfilehash: e2a6a54334f7b8a63696ead918f4f34e0c36e438
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784722"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="be5dc-103">IHostSyncManager::SetCLRSyncManager (Método)</span><span class="sxs-lookup"><span data-stu-id="be5dc-103">IHostSyncManager::SetCLRSyncManager Method</span></span>

<span data-ttu-id="be5dc-104">Establece la instancia de [ICLRSyncManager](iclrsyncmanager-interface.md) que se va a asociar a la instancia actual de [IHostSyncManager](ihostsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="be5dc-104">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be5dc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be5dc-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be5dc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be5dc-106">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="be5dc-107">de Puntero a una `ICLRSyncManager` instancia de proporcionada por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="be5dc-107">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be5dc-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="be5dc-108">Return Value</span></span>  
  
|<span data-ttu-id="be5dc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be5dc-109">HRESULT</span></span>|<span data-ttu-id="be5dc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="be5dc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be5dc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="be5dc-111">S_OK</span></span>|<span data-ttu-id="be5dc-112">`SetCLRSyncManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="be5dc-112">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="be5dc-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="be5dc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be5dc-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="be5dc-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="be5dc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="be5dc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="be5dc-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="be5dc-116">The call timed out.</span></span>|  
|<span data-ttu-id="be5dc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="be5dc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="be5dc-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="be5dc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="be5dc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="be5dc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="be5dc-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="be5dc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="be5dc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be5dc-121">E_FAIL</span></span>|<span data-ttu-id="be5dc-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="be5dc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="be5dc-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="be5dc-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="be5dc-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="be5dc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be5dc-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="be5dc-125">Remarks</span></span>  

 <span data-ttu-id="be5dc-126">Para facilitar la comunicación entre el host y el CLR, las interfaces de hospedaje generalmente están en parejas.</span><span class="sxs-lookup"><span data-stu-id="be5dc-126">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="be5dc-127">Un miembro del par se implementa mediante el host y CLR implementa el otro miembro.</span><span class="sxs-lookup"><span data-stu-id="be5dc-127">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="be5dc-128">Como implementación del lado host, la `IHostSyncManager` interfaz corresponde a la `ICLRSyncManager` interfaz implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="be5dc-128">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="be5dc-129">CLR llama `SetCLRSyncManager` a para proporcionar una `ICLRSyncManager` instancia del host que se va a asociar a la `IHostSyncManager` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="be5dc-129">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be5dc-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be5dc-130">Requirements</span></span>  

 <span data-ttu-id="be5dc-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be5dc-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be5dc-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="be5dc-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be5dc-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="be5dc-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be5dc-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be5dc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be5dc-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="be5dc-135">See also</span></span>

- [<span data-ttu-id="be5dc-136">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be5dc-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="be5dc-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be5dc-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
