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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e443ec3f743d56f0fe7e4e1c794f16bab2db8314
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763964"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="c03a8-102">IHostAutoEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="c03a8-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="c03a8-103">Establece el actual [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instancia en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="c03a8-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c03a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c03a8-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c03a8-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c03a8-105">Return Value</span></span>  
  
|<span data-ttu-id="c03a8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c03a8-106">HRESULT</span></span>|<span data-ttu-id="c03a8-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c03a8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c03a8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c03a8-108">S_OK</span></span>|<span data-ttu-id="c03a8-109">`Set` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c03a8-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="c03a8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c03a8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c03a8-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c03a8-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c03a8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c03a8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c03a8-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c03a8-113">The call timed out.</span></span>|  
|<span data-ttu-id="c03a8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c03a8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c03a8-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c03a8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c03a8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c03a8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c03a8-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="c03a8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c03a8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c03a8-118">E_FAIL</span></span>|<span data-ttu-id="c03a8-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="c03a8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c03a8-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c03a8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c03a8-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c03a8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c03a8-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c03a8-122">Requirements</span></span>  
 <span data-ttu-id="c03a8-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c03a8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c03a8-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c03a8-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c03a8-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c03a8-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c03a8-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c03a8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c03a8-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c03a8-127">See also</span></span>

- [<span data-ttu-id="c03a8-128">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c03a8-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c03a8-129">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c03a8-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c03a8-130">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c03a8-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="c03a8-131">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c03a8-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
