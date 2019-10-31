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
ms.openlocfilehash: b896c5509cc4862a6416381f89bc04a28959e091
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121453"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="8c0e9-102">IHostSecurityManager::RevertToSelf (Método)</span><span class="sxs-lookup"><span data-stu-id="8c0e9-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="8c0e9-103">Finaliza la suplantación de la identidad del usuario actual y devuelve el token del subproceso original.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c0e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c0e9-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8c0e9-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8c0e9-105">Return Value</span></span>  
  
|<span data-ttu-id="8c0e9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c0e9-106">HRESULT</span></span>|<span data-ttu-id="8c0e9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c0e9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c0e9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c0e9-108">S_OK</span></span>|<span data-ttu-id="8c0e9-109">`RevertToSelf` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="8c0e9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c0e9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c0e9-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c0e9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c0e9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c0e9-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-113">The call timed out.</span></span>|  
|<span data-ttu-id="8c0e9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c0e9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c0e9-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c0e9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c0e9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c0e9-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c0e9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c0e9-118">E_FAIL</span></span>|<span data-ttu-id="8c0e9-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c0e9-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c0e9-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c0e9-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c0e9-122">Remarks</span></span>  
 <span data-ttu-id="8c0e9-123">se llama a `RevertToSelf` para volver al token de subproceso original, después de una llamada anterior al método [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c0e9-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c0e9-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c0e9-124">Requirements</span></span>  
 <span data-ttu-id="8c0e9-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c0e9-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c0e9-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8c0e9-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c0e9-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8c0e9-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c0e9-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c0e9-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0e9-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c0e9-129">See also</span></span>

- [<span data-ttu-id="8c0e9-130">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c0e9-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="8c0e9-131">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c0e9-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="8c0e9-132">ImpersonateLoggedOnUser (método)</span><span class="sxs-lookup"><span data-stu-id="8c0e9-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
