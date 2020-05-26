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
ms.openlocfilehash: b5cd02f54a930942e1892f88fb3d8e926a6f3e1b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804568"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="611a5-102">IHostManualEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="611a5-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="611a5-103">Establece la instancia de [IHostManualEvent](ihostmanualevent-interface.md) actual en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="611a5-103">Sets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="611a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="611a5-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="611a5-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="611a5-105">Return Value</span></span>  
  
|<span data-ttu-id="611a5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="611a5-106">HRESULT</span></span>|<span data-ttu-id="611a5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="611a5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="611a5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="611a5-108">S_OK</span></span>|<span data-ttu-id="611a5-109">`Set`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="611a5-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="611a5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="611a5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="611a5-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="611a5-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="611a5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="611a5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="611a5-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="611a5-113">The call timed out.</span></span>|  
|<span data-ttu-id="611a5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="611a5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="611a5-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="611a5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="611a5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="611a5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="611a5-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="611a5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="611a5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="611a5-118">E_FAIL</span></span>|<span data-ttu-id="611a5-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="611a5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="611a5-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="611a5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="611a5-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="611a5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="611a5-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="611a5-122">Requirements</span></span>  
 <span data-ttu-id="611a5-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="611a5-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="611a5-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="611a5-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="611a5-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="611a5-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="611a5-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="611a5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="611a5-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="611a5-127">See also</span></span>

- [<span data-ttu-id="611a5-128">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="611a5-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="611a5-129">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="611a5-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="611a5-130">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="611a5-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="611a5-131">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="611a5-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="611a5-132">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="611a5-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
