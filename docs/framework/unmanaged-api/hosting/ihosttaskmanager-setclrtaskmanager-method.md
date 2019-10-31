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
ms.openlocfilehash: c674cc43065bf8ea102bec1c5134757380454913
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141229"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="76f3f-102">IHostTaskManager::SetCLRTaskManager (Método)</span><span class="sxs-lookup"><span data-stu-id="76f3f-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="76f3f-103">Proporciona al host un puntero de interfaz a una instancia de [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) implementada por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="76f3f-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76f3f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f3f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76f3f-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="76f3f-106">de Puntero a una instancia de `ICLRTaskManager` implementada por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="76f3f-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76f3f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76f3f-107">Return Value</span></span>  
  
|<span data-ttu-id="76f3f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76f3f-108">HRESULT</span></span>|<span data-ttu-id="76f3f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="76f3f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76f3f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="76f3f-110">S_OK</span></span>|<span data-ttu-id="76f3f-111">`SetCLRTaskManager` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="76f3f-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="76f3f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76f3f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76f3f-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="76f3f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="76f3f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="76f3f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="76f3f-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="76f3f-115">The call timed out.</span></span>|  
|<span data-ttu-id="76f3f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="76f3f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="76f3f-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="76f3f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="76f3f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="76f3f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="76f3f-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="76f3f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="76f3f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76f3f-120">E_FAIL</span></span>|<span data-ttu-id="76f3f-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="76f3f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="76f3f-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="76f3f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="76f3f-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="76f3f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76f3f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76f3f-124">Remarks</span></span>  
 <span data-ttu-id="76f3f-125">El Runtime llama a `SetCLRTaskManager` para proporcionar al host un puntero de interfaz a una instancia de `ICLRTaskManager`.</span><span class="sxs-lookup"><span data-stu-id="76f3f-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76f3f-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76f3f-126">Requirements</span></span>  
 <span data-ttu-id="76f3f-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76f3f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f3f-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="76f3f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76f3f-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="76f3f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76f3f-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76f3f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f3f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="76f3f-131">See also</span></span>

- [<span data-ttu-id="76f3f-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76f3f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="76f3f-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76f3f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="76f3f-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76f3f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="76f3f-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76f3f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
