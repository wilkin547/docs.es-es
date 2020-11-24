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
ms.openlocfilehash: db651e3fe51f90b84449874f2c60a12050b0350e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687117"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="a18ae-102">ICLRSyncManager::DeleteRWLockOwnerIterator (Método)</span><span class="sxs-lookup"><span data-stu-id="a18ae-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>

<span data-ttu-id="a18ae-103">Solicita que el Common Language Runtime (CLR) destruya un iterador creado por una llamada a [ICLRSyncManager:: CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="a18ae-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a18ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a18ae-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a18ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a18ae-105">Parameters</span></span>  

 `Iterator`  
 <span data-ttu-id="a18ae-106">de Iterador que se creó mediante una llamada a `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="a18ae-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a18ae-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a18ae-107">Return Value</span></span>  
  
|<span data-ttu-id="a18ae-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a18ae-108">HRESULT</span></span>|<span data-ttu-id="a18ae-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a18ae-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a18ae-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a18ae-110">S_OK</span></span>|<span data-ttu-id="a18ae-111">`DeleteRWLockOwnerIterator` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a18ae-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="a18ae-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a18ae-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a18ae-113">CLR no se ha cargado en un proceso o está en un estado en el que no puede ejecutar código administrado o procesar correctamente la llamada.</span><span class="sxs-lookup"><span data-stu-id="a18ae-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="a18ae-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a18ae-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a18ae-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a18ae-115">The call timed out.</span></span>|  
|<span data-ttu-id="a18ae-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a18ae-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a18ae-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a18ae-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a18ae-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a18ae-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a18ae-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a18ae-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a18ae-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a18ae-120">E_FAIL</span></span>|<span data-ttu-id="a18ae-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a18ae-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a18ae-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a18ae-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a18ae-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a18ae-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a18ae-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a18ae-124">Remarks</span></span>  

 <span data-ttu-id="a18ae-125">El host puede llamar a este método y `CreateRWLockOwnerIterator` asegurarse de que su implementación de subprocesos permanece sincronizada.</span><span class="sxs-lookup"><span data-stu-id="a18ae-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a18ae-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a18ae-126">Requirements</span></span>  

 <span data-ttu-id="a18ae-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a18ae-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a18ae-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a18ae-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a18ae-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a18ae-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a18ae-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a18ae-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a18ae-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a18ae-131">See also</span></span>

- [<span data-ttu-id="a18ae-132">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a18ae-132">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a18ae-133">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a18ae-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
