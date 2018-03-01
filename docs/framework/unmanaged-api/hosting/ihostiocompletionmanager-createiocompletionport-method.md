---
title: "IHostIoCompletionManager::CreateIoCompletionPort (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 230d6446460af92dbc4356977c0df4556d0229a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="d5b1e-102">IHostIoCompletionManager::CreateIoCompletionPort (Método)</span><span class="sxs-lookup"><span data-stu-id="d5b1e-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="d5b1e-103">Solicita que el host cree un nuevo puerto de finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5b1e-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5b1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5b1e-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="d5b1e-106">[out] Un puntero a un identificador para el puerto de terminación de E/S recién creado, o 0 (cero), si no se pudo crear el puerto.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5b1e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5b1e-107">Return Value</span></span>  
  
|<span data-ttu-id="d5b1e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5b1e-108">HRESULT</span></span>|<span data-ttu-id="d5b1e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5b1e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5b1e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5b1e-110">S_OK</span></span>|<span data-ttu-id="d5b1e-111">`CreateIoCompletionPort`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="d5b1e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5b1e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5b1e-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d5b1e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5b1e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5b1e-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-115">The call timed out.</span></span>|  
|<span data-ttu-id="d5b1e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5b1e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5b1e-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5b1e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5b1e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5b1e-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5b1e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5b1e-120">E_FAIL</span></span>|<span data-ttu-id="d5b1e-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5b1e-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5b1e-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d5b1e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d5b1e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d5b1e-125">No había memoria suficiente disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5b1e-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5b1e-126">Remarks</span></span>  
 <span data-ttu-id="d5b1e-127">CLR llama el `CreateIoCompletionPort` método para solicitar que el host cree un nuevo puerto de finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="d5b1e-128">Enlaza las operaciones de E/S a este puerto a través de una llamada a la [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d5b1e-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="d5b1e-129">El host informa sobre el estado a CLR mediante una llamada a [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="d5b1e-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5b1e-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5b1e-130">Requirements</span></span>  
 <span data-ttu-id="d5b1e-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5b1e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5b1e-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5b1e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5b1e-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5b1e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5b1e-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5b1e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b1e-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5b1e-135">See Also</span></span>  
 [<span data-ttu-id="d5b1e-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5b1e-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="d5b1e-137">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5b1e-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
