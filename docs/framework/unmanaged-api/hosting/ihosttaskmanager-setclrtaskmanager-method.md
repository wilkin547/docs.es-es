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
ms.openlocfilehash: 283e390b024fd1d0d6a51659b67eff82477fc64d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173555"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="13950-102">IHostTaskManager::SetCLRTaskManager (Método)</span><span class="sxs-lookup"><span data-stu-id="13950-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="13950-103">Proporciona el host con un puntero de interfaz a un [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instancia implementada por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="13950-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13950-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13950-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13950-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13950-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="13950-106">[in] Un puntero a un `ICLRTaskManager` instancia implementada por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="13950-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13950-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="13950-107">Return Value</span></span>  
  
|<span data-ttu-id="13950-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13950-108">HRESULT</span></span>|<span data-ttu-id="13950-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="13950-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13950-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="13950-110">S_OK</span></span>|<span data-ttu-id="13950-111">`SetCLRTaskManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="13950-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="13950-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="13950-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="13950-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="13950-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="13950-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="13950-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="13950-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="13950-115">The call timed out.</span></span>|  
|<span data-ttu-id="13950-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="13950-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="13950-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="13950-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="13950-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="13950-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="13950-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="13950-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="13950-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="13950-120">E_FAIL</span></span>|<span data-ttu-id="13950-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="13950-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="13950-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="13950-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="13950-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="13950-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13950-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13950-124">Remarks</span></span>  
 <span data-ttu-id="13950-125">El runtime llama a `SetCLRTaskManager` para proporcionar el host con un puntero de interfaz a un `ICLRTaskManager` instancia.</span><span class="sxs-lookup"><span data-stu-id="13950-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13950-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13950-126">Requirements</span></span>  
 <span data-ttu-id="13950-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13950-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13950-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13950-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13950-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13950-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13950-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13950-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13950-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="13950-131">See also</span></span>

- [<span data-ttu-id="13950-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13950-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="13950-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13950-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="13950-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13950-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="13950-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13950-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
