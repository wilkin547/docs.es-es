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
ms.openlocfilehash: 9d209e13360616295f166ad23c65b0c4e764af79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="e710f-102">IHostCrst::Enter (Método)</span><span class="sxs-lookup"><span data-stu-id="e710f-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="e710f-103">Entra en la sección crítica representada por el actual [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="e710f-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e710f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e710f-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e710f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e710f-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="e710f-106">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que indican qué acciones debe realizar el host si la operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="e710f-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e710f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e710f-107">Return Value</span></span>  
  
|<span data-ttu-id="e710f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e710f-108">HRESULT</span></span>|<span data-ttu-id="e710f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e710f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e710f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e710f-110">S_OK</span></span>|<span data-ttu-id="e710f-111">`Enter`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e710f-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="e710f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e710f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e710f-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e710f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e710f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e710f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e710f-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e710f-115">The call timed out.</span></span>|  
|<span data-ttu-id="e710f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e710f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e710f-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e710f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e710f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e710f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e710f-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="e710f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e710f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e710f-120">E_FAIL</span></span>|<span data-ttu-id="e710f-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="e710f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e710f-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="e710f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e710f-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e710f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e710f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e710f-124">Remarks</span></span>  
 <span data-ttu-id="e710f-125">`Enter`refleja el Win32 `EnterCriticalSection` función.</span><span class="sxs-lookup"><span data-stu-id="e710f-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e710f-126">Este método no devuelve hasta que se haya especificado la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="e710f-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e710f-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e710f-127">Requirements</span></span>  
 <span data-ttu-id="e710f-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e710f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e710f-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e710f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e710f-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e710f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e710f-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e710f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e710f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e710f-132">See Also</span></span>  
 [<span data-ttu-id="e710f-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e710f-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e710f-134">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e710f-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="e710f-135">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e710f-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
