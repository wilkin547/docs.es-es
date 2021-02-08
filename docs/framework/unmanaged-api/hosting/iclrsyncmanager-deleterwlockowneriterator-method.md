---
description: 'Más información acerca de: ICLRSyncManager::D método eleteRWLockOwnerIterator'
title: ICLRSyncManager::DeleteRWLockOwnerIterator (Método)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
ms.openlocfilehash: 7968f326f1ad92fe6e3a0f91749fb7e462e81c04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789780"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="20f0f-103">ICLRSyncManager::DeleteRWLockOwnerIterator (Método)</span><span class="sxs-lookup"><span data-stu-id="20f0f-103">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>

<span data-ttu-id="20f0f-104">Solicita que el Common Language Runtime (CLR) destruya un iterador creado por una llamada a [ICLRSyncManager:: CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="20f0f-104">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20f0f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20f0f-105">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20f0f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20f0f-106">Parameters</span></span>  

 `Iterator`  
 <span data-ttu-id="20f0f-107">de Iterador que se creó mediante una llamada a `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="20f0f-107">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20f0f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20f0f-108">Return Value</span></span>  
  
|<span data-ttu-id="20f0f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20f0f-109">HRESULT</span></span>|<span data-ttu-id="20f0f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="20f0f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20f0f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="20f0f-111">S_OK</span></span>|<span data-ttu-id="20f0f-112">`DeleteRWLockOwnerIterator` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="20f0f-112">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="20f0f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20f0f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20f0f-114">CLR no se ha cargado en un proceso o está en un estado en el que no puede ejecutar código administrado o procesar correctamente la llamada.</span><span class="sxs-lookup"><span data-stu-id="20f0f-114">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="20f0f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20f0f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20f0f-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="20f0f-116">The call timed out.</span></span>|  
|<span data-ttu-id="20f0f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20f0f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20f0f-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="20f0f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20f0f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20f0f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20f0f-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="20f0f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20f0f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20f0f-121">E_FAIL</span></span>|<span data-ttu-id="20f0f-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="20f0f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20f0f-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="20f0f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20f0f-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="20f0f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20f0f-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="20f0f-125">Remarks</span></span>  

 <span data-ttu-id="20f0f-126">El host puede llamar a este método y `CreateRWLockOwnerIterator` asegurarse de que su implementación de subprocesos permanece sincronizada.</span><span class="sxs-lookup"><span data-stu-id="20f0f-126">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20f0f-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20f0f-127">Requirements</span></span>  

 <span data-ttu-id="20f0f-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20f0f-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20f0f-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="20f0f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20f0f-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20f0f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20f0f-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20f0f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f0f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="20f0f-132">See also</span></span>

- [<span data-ttu-id="20f0f-133">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20f0f-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="20f0f-134">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20f0f-134">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
