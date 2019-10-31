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
ms.openlocfilehash: aa17f637ef71373697db5ce66e4a6540c5cc5fbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139496"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="f04df-102">IHostSecurityManager::SetThreadToken (Método)</span><span class="sxs-lookup"><span data-stu-id="f04df-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="f04df-103">Establece un identificador para el subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="f04df-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f04df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f04df-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f04df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f04df-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="f04df-106">de Identificador del token que se va a establecer para el subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="f04df-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f04df-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f04df-107">Return Value</span></span>  
  
|<span data-ttu-id="f04df-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f04df-108">HRESULT</span></span>|<span data-ttu-id="f04df-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f04df-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f04df-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f04df-110">S_OK</span></span>|<span data-ttu-id="f04df-111">`SetThreadToken` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f04df-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="f04df-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f04df-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f04df-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f04df-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f04df-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f04df-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f04df-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f04df-115">The call timed out.</span></span>|  
|<span data-ttu-id="f04df-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f04df-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f04df-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f04df-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f04df-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f04df-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f04df-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f04df-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f04df-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f04df-120">E_FAIL</span></span>|<span data-ttu-id="f04df-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f04df-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f04df-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f04df-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f04df-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f04df-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f04df-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f04df-124">Remarks</span></span>  
 <span data-ttu-id="f04df-125">`IHostSecurityManager::SetThreadToken` se comporta de forma similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras que `IHostSecurityManager::SetThreadToken` puede asociar un token solo al subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="f04df-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="f04df-126">El tipo de `HANDLE` no es compatible con COM; es decir, su tamaño es específico de un sistema operativo y requiere serialización personalizada.</span><span class="sxs-lookup"><span data-stu-id="f04df-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="f04df-127">Por lo tanto, este token solo se usa en el proceso, entre el CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="f04df-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f04df-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f04df-128">Requirements</span></span>  
 <span data-ttu-id="f04df-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f04df-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f04df-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f04df-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f04df-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f04df-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f04df-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f04df-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04df-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f04df-133">See also</span></span>

- [<span data-ttu-id="f04df-134">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f04df-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="f04df-135">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f04df-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
