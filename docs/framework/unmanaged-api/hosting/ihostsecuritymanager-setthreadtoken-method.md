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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208077"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="14d39-102">IHostSecurityManager::SetThreadToken (Método)</span><span class="sxs-lookup"><span data-stu-id="14d39-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="14d39-103">Establece un identificador para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="14d39-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14d39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14d39-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14d39-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14d39-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="14d39-106">[in] Un identificador para el token que se va a establecer para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="14d39-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14d39-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14d39-107">Return Value</span></span>  
  
|<span data-ttu-id="14d39-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14d39-108">HRESULT</span></span>|<span data-ttu-id="14d39-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="14d39-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14d39-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="14d39-110">S_OK</span></span>|`SetThreadToken` <span data-ttu-id="14d39-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="14d39-111">returned successfully.</span></span>|  
|<span data-ttu-id="14d39-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14d39-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14d39-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="14d39-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14d39-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14d39-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14d39-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="14d39-115">The call timed out.</span></span>|  
|<span data-ttu-id="14d39-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14d39-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14d39-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="14d39-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14d39-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14d39-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14d39-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="14d39-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14d39-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14d39-120">E_FAIL</span></span>|<span data-ttu-id="14d39-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="14d39-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14d39-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="14d39-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14d39-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="14d39-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14d39-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14d39-124">Remarks</span></span>  
 `IHostSecurityManager::SetThreadToken` <span data-ttu-id="14d39-125">se comporta de manera similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras `IHostSecurityManager::SetThreadToken` puede asociar un token solo con el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="14d39-125">behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="14d39-126">El `HANDLE` tipo no es compatible con COM; es decir, su tamaño es específico de un sistema operativo y se requiere cálculo de referencias personalizado.</span><span class="sxs-lookup"><span data-stu-id="14d39-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="14d39-127">Por lo tanto, este token es para su uso solo dentro del proceso, entre CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="14d39-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14d39-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14d39-128">Requirements</span></span>  
 <span data-ttu-id="14d39-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14d39-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14d39-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="14d39-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14d39-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="14d39-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="14d39-132">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="14d39-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="14d39-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="14d39-133">See also</span></span>

- [<span data-ttu-id="14d39-134">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14d39-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="14d39-135">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14d39-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
