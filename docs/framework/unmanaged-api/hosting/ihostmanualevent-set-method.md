---
title: IHostManualEvent::Set (Método)
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3756ed3bc7863411849b9d733da816e567a86628
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767310"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="ec946-102">IHostManualEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="ec946-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="ec946-103">Establece el actual [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instancia en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="ec946-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec946-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec946-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ec946-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec946-105">Return Value</span></span>  
  
|<span data-ttu-id="ec946-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec946-106">HRESULT</span></span>|<span data-ttu-id="ec946-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ec946-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec946-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec946-108">S_OK</span></span>|<span data-ttu-id="ec946-109">`Set` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ec946-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="ec946-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec946-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec946-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ec946-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec946-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec946-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec946-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ec946-113">The call timed out.</span></span>|  
|<span data-ttu-id="ec946-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec946-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec946-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ec946-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec946-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec946-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec946-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="ec946-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec946-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec946-118">E_FAIL</span></span>|<span data-ttu-id="ec946-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="ec946-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec946-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ec946-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec946-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ec946-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec946-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec946-122">Requirements</span></span>  
 <span data-ttu-id="ec946-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec946-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec946-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec946-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec946-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec946-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec946-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec946-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec946-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec946-127">See also</span></span>

- [<span data-ttu-id="ec946-128">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec946-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="ec946-129">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec946-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="ec946-130">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec946-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="ec946-131">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec946-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="ec946-132">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec946-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
