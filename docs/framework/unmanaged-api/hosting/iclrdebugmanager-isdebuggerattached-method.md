---
title: ICLRDebugManager::IsDebuggerAttached (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 404d60bf0dfb8de1d7effae01b22b15e8931757c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473947"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="3a6ae-102">ICLRDebugManager::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="3a6ae-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="3a6ae-103">Obtiene un valor que indica si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a6ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a6ae-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a6ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a6ae-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="3a6ae-106">[out] `true` si hay un depurador asociado al proceso; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a6ae-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3a6ae-107">Return Value</span></span>  
  
|<span data-ttu-id="3a6ae-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a6ae-108">HRESULT</span></span>|<span data-ttu-id="3a6ae-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a6ae-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a6ae-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a6ae-110">S_OK</span></span>|<span data-ttu-id="3a6ae-111">`IsDebuggerAttached` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="3a6ae-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3a6ae-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3a6ae-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3a6ae-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3a6ae-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3a6ae-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-115">The call timed out.</span></span>|  
|<span data-ttu-id="3a6ae-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3a6ae-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3a6ae-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3a6ae-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3a6ae-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3a6ae-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3a6ae-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a6ae-120">E_FAIL</span></span>|<span data-ttu-id="3a6ae-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3a6ae-122">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3a6ae-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a6ae-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a6ae-124">Remarks</span></span>  
 <span data-ttu-id="3a6ae-125">`IsDebuggerAttached` permite al host CLR para determinar si se adjunta un depurador al proceso de consulta.</span><span class="sxs-lookup"><span data-stu-id="3a6ae-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a6ae-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a6ae-126">Requirements</span></span>  
 <span data-ttu-id="3a6ae-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a6ae-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a6ae-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3a6ae-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a6ae-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a6ae-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a6ae-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a6ae-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a6ae-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a6ae-131">See also</span></span>
- [<span data-ttu-id="3a6ae-132">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a6ae-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3a6ae-133">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a6ae-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="3a6ae-134">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a6ae-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
