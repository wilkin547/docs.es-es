---
title: IHostSecurityManager::SetThreadToken (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71f5cdfaf47c55107980edf089f8964c5936fb23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440991"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="b6fc3-102">IHostSecurityManager::SetThreadToken (Método)</span><span class="sxs-lookup"><span data-stu-id="b6fc3-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="b6fc3-103">Establece un identificador para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6fc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6fc3-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6fc3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6fc3-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="b6fc3-106">[in] Un identificador para el símbolo (token) para establecer para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6fc3-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6fc3-107">Return Value</span></span>  
  
|<span data-ttu-id="b6fc3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6fc3-108">HRESULT</span></span>|<span data-ttu-id="b6fc3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6fc3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6fc3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6fc3-110">S_OK</span></span>|<span data-ttu-id="b6fc3-111">`SetThreadToken` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="b6fc3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b6fc3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b6fc3-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b6fc3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b6fc3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b6fc3-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-115">The call timed out.</span></span>|  
|<span data-ttu-id="b6fc3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b6fc3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b6fc3-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b6fc3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b6fc3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b6fc3-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b6fc3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b6fc3-120">E_FAIL</span></span>|<span data-ttu-id="b6fc3-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b6fc3-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b6fc3-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6fc3-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6fc3-124">Remarks</span></span>  
 <span data-ttu-id="b6fc3-125">`IHostSecurityManager::SetThreadToken` se comporta de manera similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras `IHostSecurityManager::SetThreadToken` sólo puede asociar un token del subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="b6fc3-126">El `HANDLE` tipo no es compatible con COM; es decir, su tamaño es específico de un sistema operativo y requiere el cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="b6fc3-127">Por lo tanto, este token es para su uso solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="b6fc3-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6fc3-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6fc3-128">Requirements</span></span>  
 <span data-ttu-id="b6fc3-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6fc3-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6fc3-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b6fc3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6fc3-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6fc3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6fc3-132">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6fc3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fc3-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6fc3-133">See Also</span></span>  
 [<span data-ttu-id="b6fc3-134">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6fc3-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="b6fc3-135">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6fc3-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
