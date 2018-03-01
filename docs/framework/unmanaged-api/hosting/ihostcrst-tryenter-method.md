---
title: "IHostCrst::TryEnter (Método)"
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
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1ddec99069e3cd7777e45031e7f0e8d3eabeccd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="fea23-102">IHostCrst::TryEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="fea23-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="fea23-103">Intenta entrar en la sección crítica representada por el actual [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="fea23-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea23-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fea23-104">Syntax</span></span>  
  
```  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fea23-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fea23-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="fea23-106">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que indican qué acciones debe realizar el host si la operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="fea23-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="fea23-107">[out] `true` si la sección crítica puede ser especificado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="fea23-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fea23-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fea23-108">Return Value</span></span>  
  
|<span data-ttu-id="fea23-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fea23-109">HRESULT</span></span>|<span data-ttu-id="fea23-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fea23-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fea23-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fea23-111">S_OK</span></span>|<span data-ttu-id="fea23-112">`TryEnter`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fea23-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="fea23-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fea23-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fea23-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fea23-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fea23-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fea23-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fea23-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fea23-116">The call timed out.</span></span>|  
|<span data-ttu-id="fea23-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fea23-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fea23-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fea23-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fea23-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fea23-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fea23-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="fea23-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fea23-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fea23-121">E_FAIL</span></span>|<span data-ttu-id="fea23-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="fea23-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fea23-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="fea23-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fea23-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fea23-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fea23-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fea23-125">Remarks</span></span>  
 <span data-ttu-id="fea23-126">`TryEnter`Devuelve un valor inmediatamente e indica si el subproceso que realiza la llamada entró la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="fea23-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="fea23-127">Este método refleja el Win32 `TryEnterCriticalSection` función.</span><span class="sxs-lookup"><span data-stu-id="fea23-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fea23-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fea23-128">Requirements</span></span>  
 <span data-ttu-id="fea23-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fea23-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fea23-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fea23-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fea23-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fea23-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fea23-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fea23-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea23-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="fea23-133">See Also</span></span>  
 [<span data-ttu-id="fea23-134">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fea23-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="fea23-135">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fea23-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="fea23-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fea23-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
