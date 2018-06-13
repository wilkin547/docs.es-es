---
title: IHostSecurityManager::RevertToSelf (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c34d9243e4ed7ed2492784154b157189c7d22cd2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440585"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="34d90-102">IHostSecurityManager::RevertToSelf (Método)</span><span class="sxs-lookup"><span data-stu-id="34d90-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="34d90-103">Termina la suplantación de identidad del usuario actual y devuelve el token de subproceso original.</span><span class="sxs-lookup"><span data-stu-id="34d90-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34d90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34d90-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="34d90-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="34d90-105">Return Value</span></span>  
  
|<span data-ttu-id="34d90-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="34d90-106">HRESULT</span></span>|<span data-ttu-id="34d90-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="34d90-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="34d90-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="34d90-108">S_OK</span></span>|<span data-ttu-id="34d90-109">`RevertToSelf` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="34d90-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="34d90-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="34d90-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="34d90-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="34d90-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="34d90-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="34d90-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="34d90-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="34d90-113">The call timed out.</span></span>|  
|<span data-ttu-id="34d90-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="34d90-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="34d90-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="34d90-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="34d90-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="34d90-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="34d90-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="34d90-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="34d90-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="34d90-118">E_FAIL</span></span>|<span data-ttu-id="34d90-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="34d90-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="34d90-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="34d90-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="34d90-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="34d90-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34d90-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34d90-122">Remarks</span></span>  
 <span data-ttu-id="34d90-123">`RevertToSelf` se llama para devolver al token del subproceso original, después de una llamada anterior a la [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="34d90-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34d90-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34d90-124">Requirements</span></span>  
 <span data-ttu-id="34d90-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34d90-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34d90-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34d90-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34d90-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34d90-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34d90-128">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34d90-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d90-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="34d90-129">See Also</span></span>  
 [<span data-ttu-id="34d90-130">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="34d90-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="34d90-131">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="34d90-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="34d90-132">ImpersonateLoggedOnUser (método)</span><span class="sxs-lookup"><span data-stu-id="34d90-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
