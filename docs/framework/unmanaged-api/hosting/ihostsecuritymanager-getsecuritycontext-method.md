---
title: "IHostSecurityManager::GetSecurityContext (Método)"
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
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4a5fcdf0d0244694a52cf1964d0e7c4be692df2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="e9119-102">IHostSecurityManager::GetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="e9119-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="e9119-103">Obtiene el solicitado [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) desde el host.</span><span class="sxs-lookup"><span data-stu-id="e9119-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9119-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9119-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9119-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9119-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="e9119-106">[in] Uno de los [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valores, que indica qué tipo de contexto de seguridad para devolver.</span><span class="sxs-lookup"><span data-stu-id="e9119-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="e9119-107">[out] La dirección de un puntero de interfaz a la `IHostSecurityContext` de `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="e9119-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9119-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e9119-108">Return Value</span></span>  
  
|<span data-ttu-id="e9119-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9119-109">HRESULT</span></span>|<span data-ttu-id="e9119-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9119-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9119-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9119-111">S_OK</span></span>|<span data-ttu-id="e9119-112">`GetSecurityContext`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9119-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="e9119-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e9119-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9119-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9119-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e9119-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e9119-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e9119-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e9119-116">The call timed out.</span></span>|  
|<span data-ttu-id="e9119-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e9119-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e9119-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e9119-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e9119-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e9119-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e9119-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="e9119-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e9119-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e9119-121">E_FAIL</span></span>|<span data-ttu-id="e9119-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="e9119-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e9119-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="e9119-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e9119-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e9119-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9119-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9119-125">Remarks</span></span>  
 <span data-ttu-id="e9119-126">Un host puede controlar todo el acceso de código a los tokens de subprocesos por código de usuario y CLR.</span><span class="sxs-lookup"><span data-stu-id="e9119-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="e9119-127">También puede asegurar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="e9119-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="e9119-128">`IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para CLR.</span><span class="sxs-lookup"><span data-stu-id="e9119-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="e9119-129">CLR captura esta información y mueve a través del envío de elemento de trabajo de grupo de subprocesos, la ejecución del finalizador y la construcción de módulos y de clases.</span><span class="sxs-lookup"><span data-stu-id="e9119-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9119-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9119-130">Requirements</span></span>  
 <span data-ttu-id="e9119-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9119-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9119-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9119-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9119-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9119-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9119-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9119-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9119-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9119-135">See Also</span></span>  
 [<span data-ttu-id="e9119-136">EContextType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="e9119-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="e9119-137">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9119-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="e9119-138">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9119-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
