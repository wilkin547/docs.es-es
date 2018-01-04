---
title: "IHostCrst::Enter (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Enter
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 390f30c85dac494451af1ff82328c913dd9438ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="2394c-102">IHostCrst::Enter (Método)</span><span class="sxs-lookup"><span data-stu-id="2394c-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="2394c-103">Entra en la sección crítica representada por el actual [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="2394c-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2394c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2394c-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2394c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2394c-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="2394c-106">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que indican qué acciones debe realizar el host si la operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="2394c-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2394c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2394c-107">Return Value</span></span>  
  
|<span data-ttu-id="2394c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2394c-108">HRESULT</span></span>|<span data-ttu-id="2394c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2394c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2394c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2394c-110">S_OK</span></span>|<span data-ttu-id="2394c-111">`Enter`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2394c-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="2394c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2394c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2394c-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2394c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2394c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2394c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2394c-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2394c-115">The call timed out.</span></span>|  
|<span data-ttu-id="2394c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2394c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2394c-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2394c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2394c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2394c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2394c-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="2394c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2394c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2394c-120">E_FAIL</span></span>|<span data-ttu-id="2394c-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="2394c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2394c-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2394c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2394c-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2394c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2394c-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2394c-124">Remarks</span></span>  
 <span data-ttu-id="2394c-125">`Enter`refleja el Win32 `EnterCriticalSection` función.</span><span class="sxs-lookup"><span data-stu-id="2394c-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2394c-126">Este método no devuelve hasta que se haya especificado la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="2394c-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2394c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2394c-127">Requirements</span></span>  
 <span data-ttu-id="2394c-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2394c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2394c-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2394c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2394c-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2394c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2394c-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2394c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2394c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2394c-132">See Also</span></span>  
 [<span data-ttu-id="2394c-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2394c-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="2394c-134">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2394c-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="2394c-135">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2394c-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
