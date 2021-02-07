---
description: 'Más información acerca de: IHostSecurityManager:: ImpersonateLoggedOnUser (método)'
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
ms.openlocfilehash: 7b77e0a163551a48629898b1311fc19ba815aaf4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671599"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="e0f16-103">IHostSecurityManager::ImpersonateLoggedOnUser (Método)</span><span class="sxs-lookup"><span data-stu-id="e0f16-103">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>

<span data-ttu-id="e0f16-104">Solicita que el código se ejecute con las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="e0f16-104">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0f16-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0f16-105">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0f16-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0f16-106">Parameters</span></span>  

 `hToken`  
 <span data-ttu-id="e0f16-107">de Un token que representa las credenciales del usuario que se va a suplantar.</span><span class="sxs-lookup"><span data-stu-id="e0f16-107">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0f16-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e0f16-108">Return Value</span></span>  
  
|<span data-ttu-id="e0f16-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0f16-109">HRESULT</span></span>|<span data-ttu-id="e0f16-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0f16-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0f16-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0f16-111">S_OK</span></span>|<span data-ttu-id="e0f16-112">`ImpersonateLoggedOnUser` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e0f16-112">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="e0f16-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0f16-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0f16-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e0f16-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0f16-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0f16-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0f16-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e0f16-116">The call timed out.</span></span>|  
|<span data-ttu-id="e0f16-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0f16-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0f16-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e0f16-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0f16-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0f16-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0f16-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e0f16-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0f16-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0f16-121">E_FAIL</span></span>|<span data-ttu-id="e0f16-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e0f16-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0f16-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e0f16-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0f16-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e0f16-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0f16-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e0f16-125">Remarks</span></span>  

 <span data-ttu-id="e0f16-126">Llame a `LogonUser` o a una función de Win32 relacionada para obtener un identificador de las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="e0f16-126">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="e0f16-127">El `HANDLE` tipo no es compatible con com, es decir, su tamaño es específico de un sistema operativo y requiere serialización personalizada.</span><span class="sxs-lookup"><span data-stu-id="e0f16-127">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="e0f16-128">Por lo tanto, este token solo se usa en el proceso, entre el CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="e0f16-128">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0f16-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0f16-129">Requirements</span></span>  

 <span data-ttu-id="e0f16-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0f16-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0f16-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e0f16-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0f16-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0f16-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0f16-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0f16-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f16-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0f16-134">See also</span></span>

- [<span data-ttu-id="e0f16-135">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0f16-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="e0f16-136">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0f16-136">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="e0f16-137">Método RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="e0f16-137">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)
