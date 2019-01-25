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
ms.openlocfilehash: b7994757a127686967d9863a574d0e1f8425ca86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521223"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="8a10e-102">IHostAutoEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="8a10e-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="8a10e-103">Establece el actual [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instancia en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="8a10e-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a10e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a10e-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8a10e-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8a10e-105">Return Value</span></span>  
  
|<span data-ttu-id="8a10e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a10e-106">HRESULT</span></span>|<span data-ttu-id="8a10e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a10e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a10e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a10e-108">S_OK</span></span>|<span data-ttu-id="8a10e-109">`Set` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8a10e-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="8a10e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a10e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a10e-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8a10e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a10e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a10e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a10e-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8a10e-113">The call timed out.</span></span>|  
|<span data-ttu-id="8a10e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a10e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a10e-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8a10e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a10e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a10e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a10e-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="8a10e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a10e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a10e-118">E_FAIL</span></span>|<span data-ttu-id="8a10e-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="8a10e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a10e-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8a10e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a10e-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8a10e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a10e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a10e-122">Requirements</span></span>  
 <span data-ttu-id="8a10e-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a10e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a10e-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a10e-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a10e-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a10e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a10e-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a10e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a10e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a10e-127">See also</span></span>
- [<span data-ttu-id="8a10e-128">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a10e-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8a10e-129">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a10e-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="8a10e-130">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a10e-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="8a10e-131">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a10e-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
