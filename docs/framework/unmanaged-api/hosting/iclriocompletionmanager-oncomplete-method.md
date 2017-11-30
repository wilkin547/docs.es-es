---
title: "ICLRIoCompletionManager::OnComplete (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRIoCompletionManager.OnComplete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9bd38679d1b8d099e5eb6330e03e2333b03780dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="20895-102">ICLRIoCompletionManager::OnComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="20895-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="20895-103">Notifica a common language runtime (CLR) del estado de una solicitud de E/S que se realiza mediante una llamada a la [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="20895-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20895-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20895-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20895-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20895-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="20895-106">[in] Un valor HRESULT que indica el estado de la operación de enlace.</span><span class="sxs-lookup"><span data-stu-id="20895-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="20895-107">S_OK indica que la operación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="20895-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="20895-108">HOST_E_INTERRUPTED indica que la llamada finalizó antes de completarse.</span><span class="sxs-lookup"><span data-stu-id="20895-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="20895-109">E_FAIL indica que se produjo un error grave, irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="20895-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="20895-110">[in] El número de bytes transferidos durante el procesamiento de la solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="20895-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="20895-111">[in] Un puntero a la `OVERLAPPED` estructura que se pasó a la llamada a la `IHostIoCompletionManager::Bind` método.</span><span class="sxs-lookup"><span data-stu-id="20895-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20895-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20895-112">Return Value</span></span>  
  
|<span data-ttu-id="20895-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20895-113">HRESULT</span></span>|<span data-ttu-id="20895-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="20895-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20895-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="20895-115">S_OK</span></span>|<span data-ttu-id="20895-116">`OnComplete`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="20895-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="20895-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20895-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20895-118">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="20895-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="20895-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20895-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20895-120">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="20895-120">The call timed out.</span></span>|  
|<span data-ttu-id="20895-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20895-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20895-122">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="20895-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20895-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20895-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20895-124">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="20895-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20895-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20895-125">E_FAIL</span></span>|<span data-ttu-id="20895-126">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="20895-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20895-127">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="20895-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20895-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="20895-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20895-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20895-129">Remarks</span></span>  
 <span data-ttu-id="20895-130">Si el host implementa una abstracción de finalización de E/S, el CLR realiza las solicitudes de E/S a través del host utilizando métodos de [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="20895-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="20895-131">El host, a continuación, llama al método el `OnComplete` método para notificar el tiempo de ejecución del resultado de dichas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="20895-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20895-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20895-132">Requirements</span></span>  
 <span data-ttu-id="20895-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20895-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20895-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20895-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20895-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20895-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20895-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20895-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20895-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="20895-137">See Also</span></span>  
 [<span data-ttu-id="20895-138">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20895-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="20895-139">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20895-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="20895-140">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20895-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
