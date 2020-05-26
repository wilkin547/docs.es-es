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
ms.openlocfilehash: 7891ddc5085eedd2a9010023f119d08f101e2fa3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803775"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="553a9-102">IHostSecurityManager::SetThreadToken (Método)</span><span class="sxs-lookup"><span data-stu-id="553a9-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="553a9-103">Establece un identificador para el subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="553a9-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="553a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="553a9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="553a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="553a9-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="553a9-106">de Identificador del token que se va a establecer para el subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="553a9-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="553a9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="553a9-107">Return Value</span></span>  
  
|<span data-ttu-id="553a9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="553a9-108">HRESULT</span></span>|<span data-ttu-id="553a9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="553a9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="553a9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="553a9-110">S_OK</span></span>|<span data-ttu-id="553a9-111">`SetThreadToken`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="553a9-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="553a9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="553a9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="553a9-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="553a9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="553a9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="553a9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="553a9-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="553a9-115">The call timed out.</span></span>|  
|<span data-ttu-id="553a9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="553a9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="553a9-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="553a9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="553a9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="553a9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="553a9-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="553a9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="553a9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="553a9-120">E_FAIL</span></span>|<span data-ttu-id="553a9-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="553a9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="553a9-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="553a9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="553a9-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="553a9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="553a9-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="553a9-124">Remarks</span></span>  
 <span data-ttu-id="553a9-125">`IHostSecurityManager::SetThreadToken`se comporta de forma similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras que `IHostSecurityManager::SetThreadToken` puede asociar un token solo al subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="553a9-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="553a9-126">El `HANDLE` tipo no es compatible con com; es decir, su tamaño es específico de un sistema operativo y requiere serialización personalizada.</span><span class="sxs-lookup"><span data-stu-id="553a9-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="553a9-127">Por lo tanto, este token solo se usa en el proceso, entre el CLR y el host.</span><span class="sxs-lookup"><span data-stu-id="553a9-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="553a9-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="553a9-128">Requirements</span></span>  
 <span data-ttu-id="553a9-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="553a9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="553a9-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="553a9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="553a9-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="553a9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="553a9-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="553a9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553a9-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="553a9-133">See also</span></span>

- [<span data-ttu-id="553a9-134">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="553a9-134">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="553a9-135">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="553a9-135">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
