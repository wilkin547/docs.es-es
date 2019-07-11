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
ms.openlocfilehash: bc5008461acc3b0653c53cee70cbfe89c90a440b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749395"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="7227d-102">IHostTaskManager::SetCLRTaskManager (Método)</span><span class="sxs-lookup"><span data-stu-id="7227d-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="7227d-103">Proporciona el host con un puntero de interfaz a un [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instancia implementada por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7227d-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7227d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7227d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7227d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7227d-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="7227d-106">[in] Un puntero a un `ICLRTaskManager` instancia implementada por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="7227d-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7227d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7227d-107">Return Value</span></span>  
  
|<span data-ttu-id="7227d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7227d-108">HRESULT</span></span>|<span data-ttu-id="7227d-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7227d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7227d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7227d-110">S_OK</span></span>|<span data-ttu-id="7227d-111">`SetCLRTaskManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7227d-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="7227d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7227d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7227d-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7227d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7227d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7227d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7227d-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7227d-115">The call timed out.</span></span>|  
|<span data-ttu-id="7227d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7227d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7227d-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7227d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7227d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7227d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7227d-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="7227d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7227d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7227d-120">E_FAIL</span></span>|<span data-ttu-id="7227d-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="7227d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7227d-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7227d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7227d-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7227d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7227d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7227d-124">Remarks</span></span>  
 <span data-ttu-id="7227d-125">El runtime llama a `SetCLRTaskManager` para proporcionar el host con un puntero de interfaz a un `ICLRTaskManager` instancia.</span><span class="sxs-lookup"><span data-stu-id="7227d-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7227d-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7227d-126">Requirements</span></span>  
 <span data-ttu-id="7227d-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7227d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7227d-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7227d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7227d-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7227d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7227d-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7227d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7227d-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7227d-131">See also</span></span>

- [<span data-ttu-id="7227d-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7227d-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7227d-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7227d-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7227d-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7227d-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7227d-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7227d-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
