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
ms.openlocfilehash: 1114fc744ac1811585f2c5a94858b75eda00815c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136759"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="9469a-102">IHostManualEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="9469a-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="9469a-103">Establece la instancia de [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) actual en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="9469a-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9469a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9469a-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9469a-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9469a-105">Return Value</span></span>  
  
|<span data-ttu-id="9469a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9469a-106">HRESULT</span></span>|<span data-ttu-id="9469a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9469a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9469a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9469a-108">S_OK</span></span>|<span data-ttu-id="9469a-109">`Set` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9469a-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="9469a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9469a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9469a-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9469a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9469a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9469a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9469a-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9469a-113">The call timed out.</span></span>|  
|<span data-ttu-id="9469a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9469a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9469a-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9469a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9469a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9469a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9469a-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="9469a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9469a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9469a-118">E_FAIL</span></span>|<span data-ttu-id="9469a-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="9469a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9469a-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9469a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9469a-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9469a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9469a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9469a-122">Requirements</span></span>  
 <span data-ttu-id="9469a-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9469a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9469a-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9469a-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9469a-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9469a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9469a-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9469a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9469a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9469a-127">See also</span></span>

- [<span data-ttu-id="9469a-128">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9469a-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9469a-129">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9469a-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="9469a-130">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9469a-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="9469a-131">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9469a-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="9469a-132">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9469a-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
