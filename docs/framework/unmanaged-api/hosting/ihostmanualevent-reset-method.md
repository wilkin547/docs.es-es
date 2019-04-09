---
title: IHostManualEvent::Reset (Método)
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b3de70e6bdecba6370174ee825d2dec7c14270e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148569"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="725e7-102">IHostManualEvent::Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="725e7-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="725e7-103">Restablece el actual [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instancia a un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="725e7-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="725e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="725e7-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="725e7-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="725e7-105">Return Value</span></span>  
  
|<span data-ttu-id="725e7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="725e7-106">HRESULT</span></span>|<span data-ttu-id="725e7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="725e7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="725e7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="725e7-108">S_OK</span></span>|`Reset` <span data-ttu-id="725e7-109">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="725e7-109">returned successfully.</span></span>|  
|<span data-ttu-id="725e7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="725e7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="725e7-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="725e7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="725e7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="725e7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="725e7-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="725e7-113">The call timed out.</span></span>|  
|<span data-ttu-id="725e7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="725e7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="725e7-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="725e7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="725e7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="725e7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="725e7-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="725e7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="725e7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="725e7-118">E_FAIL</span></span>|<span data-ttu-id="725e7-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="725e7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="725e7-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="725e7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="725e7-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="725e7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="725e7-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="725e7-122">Requirements</span></span>  
 <span data-ttu-id="725e7-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="725e7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="725e7-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="725e7-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="725e7-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="725e7-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="725e7-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="725e7-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="725e7-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="725e7-127">See also</span></span>

- [<span data-ttu-id="725e7-128">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="725e7-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="725e7-129">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="725e7-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="725e7-130">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="725e7-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="725e7-131">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="725e7-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="725e7-132">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="725e7-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
