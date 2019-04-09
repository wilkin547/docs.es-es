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
ms.openlocfilehash: 82988d25926a4e61d91a98e7cd5995dacde4e5b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127068"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="dbbaf-102">ICLRSyncManager::DeleteRWLockOwnerIterator (Método)</span><span class="sxs-lookup"><span data-stu-id="dbbaf-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="dbbaf-103">Solicita que common language runtime (CLR) destruya un iterador que se creó mediante una llamada a [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="dbbaf-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbbaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbbaf-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbbaf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dbbaf-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="dbbaf-106">[in] El iterador que se creó mediante una llamada a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbbaf-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dbbaf-107">Return Value</span></span>  
  
|<span data-ttu-id="dbbaf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbbaf-108">HRESULT</span></span>|<span data-ttu-id="dbbaf-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbbaf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbbaf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbbaf-110">S_OK</span></span>|`DeleteRWLockOwnerIterator` <span data-ttu-id="dbbaf-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-111">returned successfully.</span></span>|  
|<span data-ttu-id="dbbaf-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dbbaf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbbaf-113">El CLR no se ha cargado en un proceso o está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="dbbaf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbbaf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbbaf-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-115">The call timed out.</span></span>|  
|<span data-ttu-id="dbbaf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbbaf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbbaf-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbbaf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbbaf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbbaf-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbbaf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbbaf-120">E_FAIL</span></span>|<span data-ttu-id="dbbaf-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbbaf-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbbaf-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbbaf-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbbaf-124">Remarks</span></span>  
 <span data-ttu-id="dbbaf-125">El host puede llamar a este método y `CreateRWLockOwnerIterator` para asegurarse de que su implementación del subprocesamiento sigue estando sincronizada.</span><span class="sxs-lookup"><span data-stu-id="dbbaf-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbbaf-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbbaf-126">Requirements</span></span>  
 <span data-ttu-id="dbbaf-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbbaf-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbbaf-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbbaf-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbbaf-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dbbaf-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="dbbaf-130">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dbbaf-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dbbaf-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbbaf-131">See also</span></span>

- [<span data-ttu-id="dbbaf-132">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbbaf-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="dbbaf-133">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbbaf-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
