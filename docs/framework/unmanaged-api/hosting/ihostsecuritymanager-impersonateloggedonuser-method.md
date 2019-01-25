---
title: IHostSecurityManager::ImpersonateLoggedOnUser (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ceb199e027b111c8e29166d3b91027a3df2d534e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658616"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="db064-102">IHostSecurityManager::ImpersonateLoggedOnUser (Método)</span><span class="sxs-lookup"><span data-stu-id="db064-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="db064-103">Las solicitudes que se ejecuta código mediante las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="db064-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db064-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db064-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db064-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db064-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="db064-106">[in] Un token que representa las credenciales del usuario que se puede suplantar.</span><span class="sxs-lookup"><span data-stu-id="db064-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db064-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db064-107">Return Value</span></span>  
  
|<span data-ttu-id="db064-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db064-108">HRESULT</span></span>|<span data-ttu-id="db064-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="db064-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db064-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="db064-110">S_OK</span></span>|<span data-ttu-id="db064-111">`ImpersonateLoggedOnUser` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="db064-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="db064-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db064-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db064-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="db064-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db064-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db064-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db064-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="db064-115">The call timed out.</span></span>|  
|<span data-ttu-id="db064-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db064-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db064-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="db064-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db064-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db064-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db064-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="db064-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db064-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db064-120">E_FAIL</span></span>|<span data-ttu-id="db064-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="db064-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db064-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="db064-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db064-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="db064-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db064-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db064-124">Remarks</span></span>  
 <span data-ttu-id="db064-125">Llamar a `LogonUser` o una función relacionada de Win32 para obtener un identificador para las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="db064-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="db064-126">El `HANDLE` tipo no es compatible con COM, es decir, su tamaño es específico de un sistema operativo y requiere cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="db064-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="db064-127">Por lo tanto, este token es para su uso solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="db064-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db064-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db064-128">Requirements</span></span>  
 <span data-ttu-id="db064-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db064-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db064-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db064-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db064-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db064-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db064-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db064-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db064-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="db064-133">See also</span></span>
- [<span data-ttu-id="db064-134">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db064-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="db064-135">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db064-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="db064-136">RevertToSelf (método)</span><span class="sxs-lookup"><span data-stu-id="db064-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
