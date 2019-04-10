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
ms.openlocfilehash: 5af9f55bdcfe23f0b2a051b33cb1280f312820a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227020"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="d432b-102">IHostAutoEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="d432b-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="d432b-103">Establece el actual [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instancia en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="d432b-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d432b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d432b-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d432b-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d432b-105">Return Value</span></span>  
  
|<span data-ttu-id="d432b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d432b-106">HRESULT</span></span>|<span data-ttu-id="d432b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d432b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d432b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d432b-108">S_OK</span></span>|`Set` <span data-ttu-id="d432b-109">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d432b-109">returned successfully.</span></span>|  
|<span data-ttu-id="d432b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d432b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d432b-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d432b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d432b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d432b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d432b-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d432b-113">The call timed out.</span></span>|  
|<span data-ttu-id="d432b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d432b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d432b-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d432b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d432b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d432b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d432b-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="d432b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d432b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d432b-118">E_FAIL</span></span>|<span data-ttu-id="d432b-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="d432b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d432b-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d432b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d432b-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d432b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d432b-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d432b-122">Requirements</span></span>  
 <span data-ttu-id="d432b-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d432b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d432b-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d432b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d432b-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d432b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d432b-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d432b-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d432b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d432b-127">See also</span></span>

- [<span data-ttu-id="d432b-128">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d432b-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d432b-129">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d432b-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d432b-130">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d432b-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="d432b-131">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d432b-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
