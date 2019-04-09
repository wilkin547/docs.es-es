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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120073"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="20162-102">IHostSecurityManager::RevertToSelf (Método)</span><span class="sxs-lookup"><span data-stu-id="20162-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="20162-103">Termina la suplantación de identidad del usuario actual y devuelve el token de subproceso original.</span><span class="sxs-lookup"><span data-stu-id="20162-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20162-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20162-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="20162-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20162-105">Return Value</span></span>  
  
|<span data-ttu-id="20162-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20162-106">HRESULT</span></span>|<span data-ttu-id="20162-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="20162-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20162-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="20162-108">S_OK</span></span>|`RevertToSelf` <span data-ttu-id="20162-109">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="20162-109">returned successfully.</span></span>|  
|<span data-ttu-id="20162-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20162-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20162-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="20162-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="20162-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20162-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20162-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="20162-113">The call timed out.</span></span>|  
|<span data-ttu-id="20162-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20162-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20162-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="20162-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20162-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20162-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20162-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="20162-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20162-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20162-118">E_FAIL</span></span>|<span data-ttu-id="20162-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="20162-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20162-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="20162-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20162-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="20162-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20162-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20162-122">Remarks</span></span>  
 `RevertToSelf` <span data-ttu-id="20162-123">se llama para devolver al token del subproceso original, después de una llamada anterior a la [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="20162-123">is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20162-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20162-124">Requirements</span></span>  
 <span data-ttu-id="20162-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20162-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20162-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20162-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20162-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20162-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="20162-128">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="20162-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="20162-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="20162-129">See also</span></span>

- [<span data-ttu-id="20162-130">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20162-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="20162-131">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20162-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="20162-132">Método ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="20162-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
