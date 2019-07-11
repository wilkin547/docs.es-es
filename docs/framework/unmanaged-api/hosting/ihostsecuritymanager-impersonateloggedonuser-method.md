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
ms.openlocfilehash: c276fc560474ff41afd0e93173d87a76a17a1323
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781004"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="142b4-102">IHostSecurityManager::ImpersonateLoggedOnUser (Método)</span><span class="sxs-lookup"><span data-stu-id="142b4-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="142b4-103">Las solicitudes que se ejecuta código mediante las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="142b4-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142b4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="142b4-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="142b4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="142b4-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="142b4-106">[in] Un token que representa las credenciales del usuario que se puede suplantar.</span><span class="sxs-lookup"><span data-stu-id="142b4-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="142b4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="142b4-107">Return Value</span></span>  
  
|<span data-ttu-id="142b4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="142b4-108">HRESULT</span></span>|<span data-ttu-id="142b4-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="142b4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="142b4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="142b4-110">S_OK</span></span>|<span data-ttu-id="142b4-111">`ImpersonateLoggedOnUser` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="142b4-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="142b4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="142b4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="142b4-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="142b4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="142b4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="142b4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="142b4-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="142b4-115">The call timed out.</span></span>|  
|<span data-ttu-id="142b4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="142b4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="142b4-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="142b4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="142b4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="142b4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="142b4-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="142b4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="142b4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="142b4-120">E_FAIL</span></span>|<span data-ttu-id="142b4-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="142b4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="142b4-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="142b4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="142b4-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="142b4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="142b4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="142b4-124">Remarks</span></span>  
 <span data-ttu-id="142b4-125">Llamar a `LogonUser` o una función relacionada de Win32 para obtener un identificador para las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="142b4-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="142b4-126">El `HANDLE` tipo no es compatible con COM, es decir, su tamaño es específico de un sistema operativo y requiere cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="142b4-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="142b4-127">Por lo tanto, este token es para su uso solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="142b4-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="142b4-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="142b4-128">Requirements</span></span>  
 <span data-ttu-id="142b4-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="142b4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="142b4-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="142b4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="142b4-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="142b4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="142b4-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="142b4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142b4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="142b4-133">See also</span></span>

- [<span data-ttu-id="142b4-134">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="142b4-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="142b4-135">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="142b4-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="142b4-136">RevertToSelf (método)</span><span class="sxs-lookup"><span data-stu-id="142b4-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
