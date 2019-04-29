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
ms.openlocfilehash: c67471c0d88ccffbfe9b7c77809124452ccc2e5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696644"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="89bee-102">IHostSecurityManager::SetThreadToken (Método)</span><span class="sxs-lookup"><span data-stu-id="89bee-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="89bee-103">Establece un identificador para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="89bee-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89bee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89bee-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89bee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89bee-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="89bee-106">[in] Un identificador para el token que se va a establecer para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="89bee-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89bee-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="89bee-107">Return Value</span></span>  
  
|<span data-ttu-id="89bee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89bee-108">HRESULT</span></span>|<span data-ttu-id="89bee-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="89bee-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89bee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="89bee-110">S_OK</span></span>|<span data-ttu-id="89bee-111">`SetThreadToken` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="89bee-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="89bee-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89bee-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89bee-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="89bee-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89bee-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89bee-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89bee-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="89bee-115">The call timed out.</span></span>|  
|<span data-ttu-id="89bee-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89bee-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89bee-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="89bee-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89bee-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89bee-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89bee-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="89bee-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89bee-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89bee-120">E_FAIL</span></span>|<span data-ttu-id="89bee-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="89bee-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89bee-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="89bee-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89bee-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="89bee-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89bee-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89bee-124">Remarks</span></span>  
 <span data-ttu-id="89bee-125">`IHostSecurityManager::SetThreadToken` se comporta de manera similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras `IHostSecurityManager::SetThreadToken` puede asociar un token solo con el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="89bee-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="89bee-126">El `HANDLE` tipo no es compatible con COM; es decir, su tamaño es específico de un sistema operativo y se requiere cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="89bee-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="89bee-127">Por lo tanto, este token es para su uso solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="89bee-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89bee-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89bee-128">Requirements</span></span>  
 <span data-ttu-id="89bee-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89bee-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89bee-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89bee-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89bee-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89bee-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89bee-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89bee-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89bee-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="89bee-133">See also</span></span>

- [<span data-ttu-id="89bee-134">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89bee-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="89bee-135">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89bee-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
