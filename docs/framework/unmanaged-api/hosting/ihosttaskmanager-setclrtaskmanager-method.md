---
description: 'Más información acerca de: IHostTaskManager:: SetCLRTaskManager ((método)'
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
ms.openlocfilehash: 438a5b56afd42eceafb484bdf0020efbad86d052
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680881"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="8c679-103">IHostTaskManager::SetCLRTaskManager (Método)</span><span class="sxs-lookup"><span data-stu-id="8c679-103">IHostTaskManager::SetCLRTaskManager Method</span></span>

<span data-ttu-id="8c679-104">Proporciona al host un puntero de interfaz a una instancia de [ICLRTaskManager](iclrtaskmanager-interface.md) implementada por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8c679-104">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c679-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c679-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c679-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c679-106">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="8c679-107">de Puntero a una `ICLRTaskManager` instancia de implementada por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="8c679-107">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c679-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8c679-108">Return Value</span></span>  
  
|<span data-ttu-id="8c679-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c679-109">HRESULT</span></span>|<span data-ttu-id="8c679-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c679-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c679-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c679-111">S_OK</span></span>|<span data-ttu-id="8c679-112">`SetCLRTaskManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c679-112">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="8c679-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c679-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c679-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c679-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c679-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c679-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c679-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c679-116">The call timed out.</span></span>|  
|<span data-ttu-id="8c679-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c679-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c679-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8c679-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c679-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c679-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c679-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="8c679-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c679-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c679-121">E_FAIL</span></span>|<span data-ttu-id="8c679-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="8c679-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c679-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8c679-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c679-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8c679-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c679-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8c679-125">Remarks</span></span>  

 <span data-ttu-id="8c679-126">El Runtime llama `SetCLRTaskManager` a para proporcionar al host un puntero de interfaz a una `ICLRTaskManager` instancia de.</span><span class="sxs-lookup"><span data-stu-id="8c679-126">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c679-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c679-127">Requirements</span></span>  

 <span data-ttu-id="8c679-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c679-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c679-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8c679-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c679-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c679-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c679-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c679-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c679-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c679-132">See also</span></span>

- [<span data-ttu-id="8c679-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c679-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="8c679-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c679-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="8c679-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c679-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="8c679-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c679-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
