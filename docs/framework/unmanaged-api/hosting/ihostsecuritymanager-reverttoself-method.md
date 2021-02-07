---
description: 'Más información acerca de: IHostSecurityManager:: RevertToSelf (método)'
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
ms.openlocfilehash: f3488653bcb498c7521de0e368b33bc444967f21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671508"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="a4cf1-103">IHostSecurityManager::RevertToSelf (Método)</span><span class="sxs-lookup"><span data-stu-id="a4cf1-103">IHostSecurityManager::RevertToSelf Method</span></span>

<span data-ttu-id="a4cf1-104">Finaliza la suplantación de la identidad del usuario actual y devuelve el token del subproceso original.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-104">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4cf1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4cf1-105">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a4cf1-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4cf1-106">Return Value</span></span>  
  
|<span data-ttu-id="a4cf1-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4cf1-107">HRESULT</span></span>|<span data-ttu-id="a4cf1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4cf1-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4cf1-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4cf1-109">S_OK</span></span>|<span data-ttu-id="a4cf1-110">`RevertToSelf` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-110">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="a4cf1-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4cf1-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4cf1-112">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4cf1-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4cf1-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4cf1-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-114">The call timed out.</span></span>|  
|<span data-ttu-id="a4cf1-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4cf1-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4cf1-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4cf1-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4cf1-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4cf1-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4cf1-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4cf1-119">E_FAIL</span></span>|<span data-ttu-id="a4cf1-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4cf1-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4cf1-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a4cf1-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4cf1-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a4cf1-123">Remarks</span></span>  

 <span data-ttu-id="a4cf1-124">`RevertToSelf` se llama a para volver al token del subproceso original, después de una llamada anterior al método [ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a4cf1-124">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4cf1-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4cf1-125">Requirements</span></span>  

 <span data-ttu-id="a4cf1-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4cf1-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4cf1-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a4cf1-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4cf1-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4cf1-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4cf1-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4cf1-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4cf1-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4cf1-130">See also</span></span>

- [<span data-ttu-id="a4cf1-131">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4cf1-131">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="a4cf1-132">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4cf1-132">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="a4cf1-133">Método ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="a4cf1-133">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)
