---
title: "IHostSecurityManager::ImpersonateLoggedOnUser (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.ImpersonateLoggedOnUser
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c5956dcad6908f0117de7f5ff0c6632ad3bb925
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="b0723-102">IHostSecurityManager::ImpersonateLoggedOnUser (Método)</span><span class="sxs-lookup"><span data-stu-id="b0723-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="b0723-103">Las solicitudes que se ejecuta código con las credenciales de identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b0723-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0723-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0723-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0723-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0723-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="b0723-106">[in] Un token que representa las credenciales del usuario que se puede suplantar.</span><span class="sxs-lookup"><span data-stu-id="b0723-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0723-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b0723-107">Return Value</span></span>  
  
|<span data-ttu-id="b0723-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0723-108">HRESULT</span></span>|<span data-ttu-id="b0723-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0723-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0723-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0723-110">S_OK</span></span>|<span data-ttu-id="b0723-111">`ImpersonateLoggedOnUser`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0723-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="b0723-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0723-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b0723-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0723-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b0723-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b0723-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b0723-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b0723-115">The call timed out.</span></span>|  
|<span data-ttu-id="b0723-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b0723-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b0723-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b0723-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b0723-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b0723-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b0723-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b0723-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b0723-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0723-120">E_FAIL</span></span>|<span data-ttu-id="b0723-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b0723-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b0723-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b0723-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b0723-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b0723-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0723-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0723-124">Remarks</span></span>  
 <span data-ttu-id="b0723-125">Llame a `LogonUser` o una función relacionada de Win32 para obtener un identificador para las credenciales de identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b0723-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="b0723-126">El `HANDLE` tipo no es compatible con COM, es decir, su tamaño es específico de un sistema operativo, y requiere el cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0723-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="b0723-127">Por lo tanto, este token es para su uso solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="b0723-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0723-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0723-128">Requirements</span></span>  
 <span data-ttu-id="b0723-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0723-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0723-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b0723-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0723-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0723-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0723-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0723-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0723-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0723-133">See Also</span></span>  
 [<span data-ttu-id="b0723-134">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0723-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="b0723-135">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0723-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="b0723-136">RevertToSelf (método)</span><span class="sxs-lookup"><span data-stu-id="b0723-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
