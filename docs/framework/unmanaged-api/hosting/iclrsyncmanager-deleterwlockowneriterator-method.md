---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a30ac0ab8c985af04709ddd8e8e5dd9bca776dcb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759091"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="06fcd-102">ICLRSyncManager::DeleteRWLockOwnerIterator (Método)</span><span class="sxs-lookup"><span data-stu-id="06fcd-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="06fcd-103">Solicita que common language runtime (CLR) destruya un iterador que se creó mediante una llamada a [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="06fcd-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06fcd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06fcd-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06fcd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06fcd-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="06fcd-106">[in] El iterador que se creó mediante una llamada a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="06fcd-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06fcd-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="06fcd-107">Return Value</span></span>  
  
|<span data-ttu-id="06fcd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06fcd-108">HRESULT</span></span>|<span data-ttu-id="06fcd-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="06fcd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06fcd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="06fcd-110">S_OK</span></span>|<span data-ttu-id="06fcd-111">`DeleteRWLockOwnerIterator` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="06fcd-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="06fcd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06fcd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06fcd-113">El CLR no se ha cargado en un proceso o está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="06fcd-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="06fcd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="06fcd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="06fcd-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="06fcd-115">The call timed out.</span></span>|  
|<span data-ttu-id="06fcd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="06fcd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="06fcd-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="06fcd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="06fcd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="06fcd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="06fcd-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="06fcd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="06fcd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06fcd-120">E_FAIL</span></span>|<span data-ttu-id="06fcd-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="06fcd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="06fcd-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="06fcd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="06fcd-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="06fcd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06fcd-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06fcd-124">Remarks</span></span>  
 <span data-ttu-id="06fcd-125">El host puede llamar a este método y `CreateRWLockOwnerIterator` para asegurarse de que su implementación del subprocesamiento sigue estando sincronizada.</span><span class="sxs-lookup"><span data-stu-id="06fcd-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06fcd-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06fcd-126">Requirements</span></span>  
 <span data-ttu-id="06fcd-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06fcd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06fcd-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06fcd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06fcd-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06fcd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06fcd-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06fcd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06fcd-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="06fcd-131">See also</span></span>

- [<span data-ttu-id="06fcd-132">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06fcd-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="06fcd-133">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06fcd-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
