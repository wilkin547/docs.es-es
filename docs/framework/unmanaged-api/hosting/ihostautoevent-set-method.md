---
title: IHostAutoEvent::Set (Método)
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
ms.openlocfilehash: 792b735522580eb7460da703899a00781e525419
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124446"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="690ae-102">IHostAutoEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="690ae-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="690ae-103">Establece la instancia de [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) actual en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="690ae-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="690ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="690ae-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="690ae-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="690ae-105">Return Value</span></span>  
  
|<span data-ttu-id="690ae-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="690ae-106">HRESULT</span></span>|<span data-ttu-id="690ae-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="690ae-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="690ae-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="690ae-108">S_OK</span></span>|<span data-ttu-id="690ae-109">`Set` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="690ae-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="690ae-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="690ae-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="690ae-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="690ae-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="690ae-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="690ae-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="690ae-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="690ae-113">The call timed out.</span></span>|  
|<span data-ttu-id="690ae-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="690ae-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="690ae-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="690ae-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="690ae-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="690ae-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="690ae-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="690ae-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="690ae-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="690ae-118">E_FAIL</span></span>|<span data-ttu-id="690ae-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="690ae-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="690ae-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="690ae-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="690ae-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="690ae-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="690ae-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="690ae-122">Requirements</span></span>  
 <span data-ttu-id="690ae-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="690ae-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="690ae-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="690ae-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="690ae-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="690ae-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="690ae-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="690ae-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="690ae-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="690ae-127">See also</span></span>

- [<span data-ttu-id="690ae-128">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="690ae-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="690ae-129">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="690ae-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="690ae-130">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="690ae-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="690ae-131">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="690ae-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
