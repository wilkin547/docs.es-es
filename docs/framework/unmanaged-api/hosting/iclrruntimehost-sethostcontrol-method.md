---
title: "ICLRRuntimeHost::SetHostControl (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.SetHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 932ba5577ee262b2b044fe5cd7681de1f8b459f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="a93a5-102">ICLRRuntimeHost::SetHostControl (Método)</span><span class="sxs-lookup"><span data-stu-id="a93a5-102">ICLRRuntimeHost::SetHostControl Method</span></span>
<span data-ttu-id="a93a5-103">Establece el puntero de interfaz que puede utilizar common language runtime (CLR) para obtener la implementación del host de [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a93a5-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a93a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a93a5-104">Syntax</span></span>  
  
```  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a93a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a93a5-105">Parameters</span></span>  
 `pHostControl`  
 <span data-ttu-id="a93a5-106">[in] Un puntero de interfaz a la implementación del host de [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a93a5-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a93a5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a93a5-107">Return Value</span></span>  
  
|<span data-ttu-id="a93a5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a93a5-108">HRESULT</span></span>|<span data-ttu-id="a93a5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a93a5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a93a5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a93a5-110">S_OK</span></span>|<span data-ttu-id="a93a5-111">`SetHostControl`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a93a5-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="a93a5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a93a5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a93a5-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a93a5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a93a5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a93a5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a93a5-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a93a5-115">The call timed out.</span></span>|  
|<span data-ttu-id="a93a5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a93a5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a93a5-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a93a5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a93a5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a93a5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a93a5-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="a93a5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a93a5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a93a5-120">E_FAIL</span></span>|<span data-ttu-id="a93a5-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="a93a5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a93a5-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a93a5-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a93a5-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a93a5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a93a5-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="a93a5-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="a93a5-125">Ya se inicializó el CLR.</span><span class="sxs-lookup"><span data-stu-id="a93a5-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a93a5-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a93a5-126">Remarks</span></span>  
 <span data-ttu-id="a93a5-127">Debe llamar a `SetHostControl` antes de que se inicializa el CLR, es decir, antes de llamar a [método Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) o usar cualquiera de los [Interfaces de metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="a93a5-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="a93a5-128">Se recomienda llamar a `SetHostControl` inmediatamente después de llamar a [CorBindToCurrentRuntime (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) o [CorBindToRuntimeEx (función)](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span><span class="sxs-lookup"><span data-stu-id="a93a5-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a93a5-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a93a5-129">Requirements</span></span>  
 <span data-ttu-id="a93a5-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a93a5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a93a5-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a93a5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a93a5-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a93a5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a93a5-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a93a5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93a5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a93a5-134">See Also</span></span>  
 [<span data-ttu-id="a93a5-135">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a93a5-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="a93a5-136">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a93a5-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
