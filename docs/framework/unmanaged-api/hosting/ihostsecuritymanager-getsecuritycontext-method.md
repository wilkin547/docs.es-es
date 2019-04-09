---
title: IHostSecurityManager::GetSecurityContext (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f4f923e868b72e9de33884e4814ebfa329a16e2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105838"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="16fd6-102">IHostSecurityManager::GetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="16fd6-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="16fd6-103">Obtiene el solicitado [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) desde el host.</span><span class="sxs-lookup"><span data-stu-id="16fd6-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16fd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16fd6-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16fd6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="16fd6-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="16fd6-106">[in] Uno de los [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valores, que indica qué tipo de contexto de seguridad para devolver.</span><span class="sxs-lookup"><span data-stu-id="16fd6-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="16fd6-107">[out] La dirección del puntero de interfaz a la `IHostSecurityContext` de `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="16fd6-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16fd6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="16fd6-108">Return Value</span></span>  
  
|<span data-ttu-id="16fd6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16fd6-109">HRESULT</span></span>|<span data-ttu-id="16fd6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="16fd6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16fd6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="16fd6-111">S_OK</span></span>|`GetSecurityContext` <span data-ttu-id="16fd6-112">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="16fd6-112">returned successfully.</span></span>|  
|<span data-ttu-id="16fd6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16fd6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16fd6-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="16fd6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16fd6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16fd6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16fd6-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="16fd6-116">The call timed out.</span></span>|  
|<span data-ttu-id="16fd6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16fd6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16fd6-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="16fd6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16fd6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16fd6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16fd6-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="16fd6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16fd6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16fd6-121">E_FAIL</span></span>|<span data-ttu-id="16fd6-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="16fd6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16fd6-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="16fd6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16fd6-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="16fd6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16fd6-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16fd6-125">Remarks</span></span>  
 <span data-ttu-id="16fd6-126">Un host puede controlar todo el acceso de código a los tokens de subprocesos por código de usuario y el CLR.</span><span class="sxs-lookup"><span data-stu-id="16fd6-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="16fd6-127">También puede garantizar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="16fd6-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> `IHostSecurityContext` <span data-ttu-id="16fd6-128">encapsula esta información de contexto de seguridad, que es opaca para el CLR.</span><span class="sxs-lookup"><span data-stu-id="16fd6-128">encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="16fd6-129">CLR captura esta información y mueve a través del envío de elemento de trabajo de grupo de subprocesos, la ejecución del finalizador y la construcción de módulo y clase.</span><span class="sxs-lookup"><span data-stu-id="16fd6-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16fd6-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16fd6-130">Requirements</span></span>  
 <span data-ttu-id="16fd6-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16fd6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16fd6-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16fd6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16fd6-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16fd6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="16fd6-134">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="16fd6-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16fd6-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="16fd6-135">See also</span></span>

- [<span data-ttu-id="16fd6-136">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="16fd6-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="16fd6-137">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16fd6-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="16fd6-138">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="16fd6-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
