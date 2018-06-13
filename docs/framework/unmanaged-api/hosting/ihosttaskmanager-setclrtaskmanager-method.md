---
title: IHostTaskManager::SetCLRTaskManager (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84501ae5e96a2eab4c5da4d4cb211fc60822e339
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445304"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="b9b72-102">IHostTaskManager::SetCLRTaskManager (Método)</span><span class="sxs-lookup"><span data-stu-id="b9b72-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="b9b72-103">Proporciona el host con un puntero de interfaz a una [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instancia implementada por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b9b72-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9b72-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9b72-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9b72-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="b9b72-106">[in] Un puntero a un `ICLRTaskManager` instancia implementada por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="b9b72-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9b72-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9b72-107">Return Value</span></span>  
  
|<span data-ttu-id="b9b72-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9b72-108">HRESULT</span></span>|<span data-ttu-id="b9b72-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9b72-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9b72-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9b72-110">S_OK</span></span>|<span data-ttu-id="b9b72-111">`SetCLRTaskManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b9b72-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="b9b72-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9b72-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9b72-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b9b72-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9b72-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9b72-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9b72-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b9b72-115">The call timed out.</span></span>|  
|<span data-ttu-id="b9b72-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9b72-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9b72-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b9b72-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9b72-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9b72-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9b72-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b9b72-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9b72-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9b72-120">E_FAIL</span></span>|<span data-ttu-id="b9b72-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b9b72-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9b72-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b9b72-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9b72-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b9b72-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9b72-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9b72-124">Remarks</span></span>  
 <span data-ttu-id="b9b72-125">El runtime llama `SetCLRTaskManager` para proporcionar al host un puntero de interfaz a un `ICLRTaskManager` instancia.</span><span class="sxs-lookup"><span data-stu-id="b9b72-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b72-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9b72-126">Requirements</span></span>  
 <span data-ttu-id="b9b72-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9b72-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b72-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9b72-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9b72-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9b72-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9b72-130">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b72-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b72-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9b72-131">See Also</span></span>  
 [<span data-ttu-id="b9b72-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9b72-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="b9b72-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9b72-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="b9b72-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9b72-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="b9b72-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9b72-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
