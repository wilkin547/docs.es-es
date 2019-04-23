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
ms.openlocfilehash: d282f6d37a2be8a41f4fbda579b3b467b9bfc8ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120073"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="4113a-102">IHostSecurityManager::RevertToSelf (Método)</span><span class="sxs-lookup"><span data-stu-id="4113a-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="4113a-103">Termina la suplantación de identidad del usuario actual y devuelve el token de subproceso original.</span><span class="sxs-lookup"><span data-stu-id="4113a-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4113a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4113a-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4113a-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4113a-105">Return Value</span></span>  
  
|<span data-ttu-id="4113a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4113a-106">HRESULT</span></span>|<span data-ttu-id="4113a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4113a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4113a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4113a-108">S_OK</span></span>|<span data-ttu-id="4113a-109">`RevertToSelf` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4113a-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="4113a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4113a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4113a-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4113a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4113a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4113a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4113a-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4113a-113">The call timed out.</span></span>|  
|<span data-ttu-id="4113a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4113a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4113a-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4113a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4113a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4113a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4113a-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="4113a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4113a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4113a-118">E_FAIL</span></span>|<span data-ttu-id="4113a-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="4113a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4113a-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4113a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4113a-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4113a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4113a-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4113a-122">Remarks</span></span>  
 <span data-ttu-id="4113a-123">`RevertToSelf` se llama para devolver al token del subproceso original, después de una llamada anterior a la [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4113a-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4113a-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4113a-124">Requirements</span></span>  
 <span data-ttu-id="4113a-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4113a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4113a-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4113a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4113a-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4113a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4113a-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4113a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4113a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4113a-129">See also</span></span>

- [<span data-ttu-id="4113a-130">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4113a-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4113a-131">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4113a-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="4113a-132">ImpersonateLoggedOnUser (método)</span><span class="sxs-lookup"><span data-stu-id="4113a-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
