---
title: "IHostSecurityManager::OpenThreadToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.OpenThreadToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b5c39632d7628d30149a0a0278f9bf6c865bc29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="db7fd-102">IHostSecurityManager::OpenThreadToken (Método)</span><span class="sxs-lookup"><span data-stu-id="db7fd-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="db7fd-103">Se abre el token de acceso discrecional asociado con el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="db7fd-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db7fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db7fd-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db7fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db7fd-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="db7fd-106">[in] Una máscara de valores de acceso que especifican los tipos solicitados de acceso al token de subproceso.</span><span class="sxs-lookup"><span data-stu-id="db7fd-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="db7fd-107">Estos valores se definen en Win32 `OpenThreadToken` función.</span><span class="sxs-lookup"><span data-stu-id="db7fd-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="db7fd-108">Los tipos de acceso solicitados se reconcilian con la lista de control de acceso discrecional (DACL) para determinar qué tipos de acceso para conceder o denegar del token.</span><span class="sxs-lookup"><span data-stu-id="db7fd-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="db7fd-109">[in] `true` para especificar que la comprobación del acceso debe realizarse utilizando el contexto de seguridad del proceso para el subproceso que realiza la llamada; `false` para especificar que la comprobación del acceso debe realizarse utilizando el contexto de seguridad para el propio subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="db7fd-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="db7fd-110">Si el subproceso está suplantando a un cliente, el contexto de seguridad puede ser de un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="db7fd-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="db7fd-111">[out] Un puntero al token de acceso recién abierto.</span><span class="sxs-lookup"><span data-stu-id="db7fd-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db7fd-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db7fd-112">Return Value</span></span>  
  
|<span data-ttu-id="db7fd-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db7fd-113">HRESULT</span></span>|<span data-ttu-id="db7fd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="db7fd-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db7fd-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="db7fd-115">S_OK</span></span>|<span data-ttu-id="db7fd-116">`OpenThreadToken`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="db7fd-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="db7fd-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db7fd-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db7fd-118">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="db7fd-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db7fd-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db7fd-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db7fd-120">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="db7fd-120">The call timed out.</span></span>|  
|<span data-ttu-id="db7fd-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db7fd-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db7fd-122">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="db7fd-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db7fd-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db7fd-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db7fd-124">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="db7fd-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db7fd-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db7fd-125">E_FAIL</span></span>|<span data-ttu-id="db7fd-126">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="db7fd-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db7fd-127">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="db7fd-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db7fd-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="db7fd-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db7fd-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db7fd-129">Remarks</span></span>  
 <span data-ttu-id="db7fd-130">`IHostSecurityManager::OpenThreadToken`se comporta de manera similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras `IHostSecurityManager::OpenThreadToken` sólo abre el token asociado al subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="db7fd-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="db7fd-131">El `HANDLE` tipo no es compatible con COM, es decir, su tamaño es específico para el sistema operativo, y requiere el cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="db7fd-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="db7fd-132">Por lo tanto, este token es para su uso solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="db7fd-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db7fd-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db7fd-133">Requirements</span></span>  
 <span data-ttu-id="db7fd-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db7fd-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db7fd-135">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db7fd-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db7fd-136">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db7fd-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db7fd-137">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db7fd-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7fd-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="db7fd-138">See Also</span></span>  
 [<span data-ttu-id="db7fd-139">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db7fd-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="db7fd-140">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db7fd-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
