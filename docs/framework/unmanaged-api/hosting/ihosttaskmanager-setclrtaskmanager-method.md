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
ms.openlocfilehash: 0e030a33a0a3368f35c82fad33f1ea2ce32446af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841833"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="6602a-102">IHostTaskManager::SetCLRTaskManager (Método)</span><span class="sxs-lookup"><span data-stu-id="6602a-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="6602a-103">Proporciona al host un puntero de interfaz a una instancia de [ICLRTaskManager](iclrtaskmanager-interface.md) implementada por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6602a-103">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6602a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6602a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6602a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6602a-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="6602a-106">de Puntero a una `ICLRTaskManager` instancia de implementada por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6602a-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6602a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6602a-107">Return Value</span></span>  
  
|<span data-ttu-id="6602a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6602a-108">HRESULT</span></span>|<span data-ttu-id="6602a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6602a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6602a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6602a-110">S_OK</span></span>|<span data-ttu-id="6602a-111">`SetCLRTaskManager`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6602a-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="6602a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6602a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6602a-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6602a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6602a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6602a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6602a-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6602a-115">The call timed out.</span></span>|  
|<span data-ttu-id="6602a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6602a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6602a-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6602a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6602a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6602a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6602a-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="6602a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6602a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6602a-120">E_FAIL</span></span>|<span data-ttu-id="6602a-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6602a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6602a-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6602a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6602a-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6602a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6602a-124">Notas</span><span class="sxs-lookup"><span data-stu-id="6602a-124">Remarks</span></span>  
 <span data-ttu-id="6602a-125">El Runtime llama `SetCLRTaskManager` a para proporcionar al host un puntero de interfaz a una `ICLRTaskManager` instancia de.</span><span class="sxs-lookup"><span data-stu-id="6602a-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6602a-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6602a-126">Requirements</span></span>  
 <span data-ttu-id="6602a-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6602a-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6602a-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6602a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6602a-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6602a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6602a-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6602a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6602a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6602a-131">See also</span></span>

- [<span data-ttu-id="6602a-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6602a-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6602a-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6602a-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6602a-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6602a-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6602a-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6602a-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
