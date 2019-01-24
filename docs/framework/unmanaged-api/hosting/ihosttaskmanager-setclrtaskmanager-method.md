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
ms.openlocfilehash: 0d18ccc18afa3bb3b7079139886c308882b2efc8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616659"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="2d2d3-102">IHostTaskManager::SetCLRTaskManager (Método)</span><span class="sxs-lookup"><span data-stu-id="2d2d3-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="2d2d3-103">Proporciona el host con un puntero de interfaz a un [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instancia implementada por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2d2d3-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d2d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d2d3-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d2d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d2d3-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="2d2d3-106">[in] Un puntero a un `ICLRTaskManager` instancia implementada por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d2d3-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d2d3-107">Return Value</span></span>  
  
|<span data-ttu-id="2d2d3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d2d3-108">HRESULT</span></span>|<span data-ttu-id="2d2d3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d2d3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d2d3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d2d3-110">S_OK</span></span>|<span data-ttu-id="2d2d3-111">`SetCLRTaskManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="2d2d3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d2d3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d2d3-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d2d3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d2d3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d2d3-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-115">The call timed out.</span></span>|  
|<span data-ttu-id="2d2d3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d2d3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d2d3-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d2d3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d2d3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d2d3-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d2d3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d2d3-120">E_FAIL</span></span>|<span data-ttu-id="2d2d3-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d2d3-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d2d3-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d2d3-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d2d3-124">Remarks</span></span>  
 <span data-ttu-id="2d2d3-125">El runtime llama a `SetCLRTaskManager` para proporcionar el host con un puntero de interfaz a un `ICLRTaskManager` instancia.</span><span class="sxs-lookup"><span data-stu-id="2d2d3-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d2d3-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d2d3-126">Requirements</span></span>  
 <span data-ttu-id="2d2d3-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d2d3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d2d3-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d2d3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d2d3-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d2d3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d2d3-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d2d3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d2d3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d2d3-131">See also</span></span>
- [<span data-ttu-id="2d2d3-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d2d3-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2d2d3-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d2d3-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2d2d3-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d2d3-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2d2d3-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d2d3-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
