---
title: "IHostSecurityContext::Capture (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext.Capture
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: def431dd40c6dd7aa6688a638971d3676bbd1ffb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="dbcc8-102">IHostSecurityContext::Capture (Método)</span><span class="sxs-lookup"><span data-stu-id="dbcc8-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="dbcc8-103">Obtiene un clon de la [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) devuelve la instancia de una llamada a [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="dbcc8-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbcc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbcc8-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbcc8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dbcc8-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="dbcc8-106">[out] Un puntero a la dirección de un clon de la `IHostSecurityContext` objeto que va a capturar.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbcc8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dbcc8-107">Return Value</span></span>  
  
|<span data-ttu-id="dbcc8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbcc8-108">HRESULT</span></span>|<span data-ttu-id="dbcc8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbcc8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbcc8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbcc8-110">S_OK</span></span>|<span data-ttu-id="dbcc8-111">`Capture`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="dbcc8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dbcc8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbcc8-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dbcc8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbcc8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbcc8-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-115">The call timed out.</span></span>|  
|<span data-ttu-id="dbcc8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbcc8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbcc8-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbcc8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbcc8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbcc8-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbcc8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbcc8-120">E_FAIL</span></span>|<span data-ttu-id="dbcc8-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbcc8-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbcc8-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbcc8-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbcc8-124">Remarks</span></span>  
 <span data-ttu-id="dbcc8-125">El puntero de interfaz devuelto desde `Capture` es un clon del contexto capturado.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="dbcc8-126">Cuando esta información se mueve a través de un punto de código asincrónico, su duración se separa de la el puntero en el que se realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="dbcc8-127">Puede liberarse, por lo tanto, el puntero original.</span><span class="sxs-lookup"><span data-stu-id="dbcc8-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbcc8-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbcc8-128">Requirements</span></span>  
 <span data-ttu-id="dbcc8-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbcc8-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbcc8-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbcc8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbcc8-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dbcc8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbcc8-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbcc8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbcc8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbcc8-133">See Also</span></span>  
 [<span data-ttu-id="dbcc8-134">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbcc8-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="dbcc8-135">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbcc8-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
