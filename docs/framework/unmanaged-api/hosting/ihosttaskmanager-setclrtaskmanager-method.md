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
ms.openlocfilehash: 23d0679599c681468caa2507518d0ae3144ac26a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669814"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="dc996-102">IHostTaskManager::SetCLRTaskManager (Método)</span><span class="sxs-lookup"><span data-stu-id="dc996-102">IHostTaskManager::SetCLRTaskManager Method</span></span>

<span data-ttu-id="dc996-103">Proporciona al host un puntero de interfaz a una instancia de [ICLRTaskManager](iclrtaskmanager-interface.md) implementada por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dc996-103">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc996-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc996-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc996-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc996-105">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="dc996-106">de Puntero a una `ICLRTaskManager` instancia de implementada por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="dc996-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc996-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dc996-107">Return Value</span></span>  
  
|<span data-ttu-id="dc996-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc996-108">HRESULT</span></span>|<span data-ttu-id="dc996-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc996-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc996-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc996-110">S_OK</span></span>|<span data-ttu-id="dc996-111">`SetCLRTaskManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc996-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="dc996-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc996-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc996-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc996-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc996-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc996-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc996-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="dc996-115">The call timed out.</span></span>|  
|<span data-ttu-id="dc996-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc996-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc996-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dc996-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc996-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc996-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc996-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="dc996-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc996-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc996-120">E_FAIL</span></span>|<span data-ttu-id="dc996-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="dc996-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc996-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="dc996-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc996-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dc996-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc996-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc996-124">Remarks</span></span>  

 <span data-ttu-id="dc996-125">El Runtime llama `SetCLRTaskManager` a para proporcionar al host un puntero de interfaz a una `ICLRTaskManager` instancia de.</span><span class="sxs-lookup"><span data-stu-id="dc996-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc996-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc996-126">Requirements</span></span>  

 <span data-ttu-id="dc996-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc996-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc996-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dc996-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc996-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc996-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc996-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc996-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc996-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc996-131">See also</span></span>

- [<span data-ttu-id="dc996-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc996-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="dc996-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc996-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="dc996-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc996-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="dc996-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc996-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
