---
title: "IHostCrst::Leave (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 391aff3920e7ea2ef010ce7d97bdedb4e636dc86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="479f8-102">IHostCrst::Leave (Método)</span><span class="sxs-lookup"><span data-stu-id="479f8-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="479f8-103">Deja la sección crítica representada por la instancia actual de [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="479f8-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="479f8-104">Syntax</span></span>  
  
```  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="479f8-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="479f8-105">Return Value</span></span>  
  
|<span data-ttu-id="479f8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="479f8-106">HRESULT</span></span>|<span data-ttu-id="479f8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="479f8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="479f8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="479f8-108">S_OK</span></span>|<span data-ttu-id="479f8-109">`Leave`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="479f8-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="479f8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="479f8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="479f8-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="479f8-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="479f8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="479f8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="479f8-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="479f8-113">The call timed out.</span></span>|  
|<span data-ttu-id="479f8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="479f8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="479f8-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="479f8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="479f8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="479f8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="479f8-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="479f8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="479f8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="479f8-118">E_FAIL</span></span>|<span data-ttu-id="479f8-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="479f8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="479f8-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="479f8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="479f8-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="479f8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="479f8-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="479f8-122">Remarks</span></span>  
 <span data-ttu-id="479f8-123">`Leave`permite que el CLR para comunicarse directamente con implementación del subprocesamiento, en el host de la lugar de usar Win32 correspondientes `LeaveCriticalSection` función.</span><span class="sxs-lookup"><span data-stu-id="479f8-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="479f8-124">Un subproceso que toma posesión de la sección crítica representada por el actual `IHostCrst` instancia debe llamar a `Leave` una vez por cada vez que entre en dicha sección crítica.</span><span class="sxs-lookup"><span data-stu-id="479f8-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="479f8-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="479f8-125">Requirements</span></span>  
 <span data-ttu-id="479f8-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="479f8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="479f8-127">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="479f8-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="479f8-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="479f8-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="479f8-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479f8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479f8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="479f8-130">See Also</span></span>  
 [<span data-ttu-id="479f8-131">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="479f8-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="479f8-132">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="479f8-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="479f8-133">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="479f8-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
