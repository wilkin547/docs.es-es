---
title: ICLRIoCompletionManager::OnComplete (Método)
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c3d4674280bf5aa459fec2b195c3164c75c6c3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779635"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="1724b-102">ICLRIoCompletionManager::OnComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="1724b-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="1724b-103">Notifica a common language runtime (CLR) del estado de una solicitud de E/S que se hace mediante una llamada a la [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1724b-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1724b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1724b-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1724b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1724b-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="1724b-106">[in] Un valor HRESULT que indica el estado de la operación de enlace.</span><span class="sxs-lookup"><span data-stu-id="1724b-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="1724b-107">S_OK indica que la operación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1724b-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="1724b-108">HOST_E_INTERRUPTED indica que la llamada finalizó antes de completarse.</span><span class="sxs-lookup"><span data-stu-id="1724b-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="1724b-109">E_FAIL indica que se produjo un error catastrófico, irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="1724b-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="1724b-110">[in] El número de bytes transferidos durante el procesamiento de la solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="1724b-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="1724b-111">[in] Un puntero a la `OVERLAPPED` estructura que se pasó a la llamada a la `IHostIoCompletionManager::Bind` método.</span><span class="sxs-lookup"><span data-stu-id="1724b-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1724b-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1724b-112">Return Value</span></span>  
  
|<span data-ttu-id="1724b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1724b-113">HRESULT</span></span>|<span data-ttu-id="1724b-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1724b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1724b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="1724b-115">S_OK</span></span>|<span data-ttu-id="1724b-116">`OnComplete` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1724b-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="1724b-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1724b-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1724b-118">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1724b-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1724b-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1724b-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1724b-120">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1724b-120">The call timed out.</span></span>|  
|<span data-ttu-id="1724b-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1724b-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1724b-122">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1724b-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1724b-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1724b-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1724b-124">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="1724b-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1724b-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1724b-125">E_FAIL</span></span>|<span data-ttu-id="1724b-126">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="1724b-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1724b-127">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1724b-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1724b-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1724b-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1724b-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1724b-129">Remarks</span></span>  
 <span data-ttu-id="1724b-130">Si el host implementa una abstracción de finalización de E/S, el CLR realiza las solicitudes de E/S a través del host mediante el uso de métodos de [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1724b-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="1724b-131">El host, a continuación, llama el `OnComplete` método para notificar el tiempo de ejecución del resultado de dichas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="1724b-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1724b-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1724b-132">Requirements</span></span>  
 <span data-ttu-id="1724b-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1724b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1724b-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1724b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1724b-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1724b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1724b-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1724b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1724b-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="1724b-137">See also</span></span>

- [<span data-ttu-id="1724b-138">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1724b-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="1724b-139">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1724b-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="1724b-140">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1724b-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
