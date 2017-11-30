---
title: "IHostIoCompletionManager::SetCLRIoCompletionManager (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetCLRIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2447ba9cf3ee5968bde26b0a578cc06ef5c614c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="0486a-102">IHostIoCompletionManager::SetCLRIoCompletionManager (Método)</span><span class="sxs-lookup"><span data-stu-id="0486a-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="0486a-103">Proporciona el host con un puntero de interfaz a la [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instancia implementada por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0486a-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0486a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0486a-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0486a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0486a-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="0486a-106">[in] Un puntero de interfaz a un `ICLRIoCompletionManager` instancia proporcionada por el CLR.</span><span class="sxs-lookup"><span data-stu-id="0486a-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0486a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0486a-107">Return Value</span></span>  
  
|<span data-ttu-id="0486a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0486a-108">HRESULT</span></span>|<span data-ttu-id="0486a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0486a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0486a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0486a-110">S_OK</span></span>|<span data-ttu-id="0486a-111">`SetCLRIoCompletionManager`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0486a-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="0486a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0486a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0486a-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0486a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0486a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0486a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0486a-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0486a-115">The call timed out.</span></span>|  
|<span data-ttu-id="0486a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0486a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0486a-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0486a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0486a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0486a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0486a-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="0486a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0486a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0486a-120">E_FAIL</span></span>|<span data-ttu-id="0486a-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="0486a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0486a-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="0486a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0486a-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0486a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0486a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0486a-124">Remarks</span></span>  
 <span data-ttu-id="0486a-125">Después de que el CLR ha llamado a `SetCLRIoCompletionManager`, el host debe llamar a [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) para notificar a CLR cuando se ha completado una solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="0486a-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0486a-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0486a-126">Requirements</span></span>  
 <span data-ttu-id="0486a-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0486a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0486a-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0486a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0486a-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0486a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0486a-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0486a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0486a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="0486a-131">See Also</span></span>  
 [<span data-ttu-id="0486a-132">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0486a-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="0486a-133">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0486a-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
