---
title: ICLRGCManager::Collect (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
ms.openlocfilehash: a7dae98d1f2dc2448bd3a5df2d6143b7be0bb734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129257"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="4d90b-102">ICLRGCManager::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="4d90b-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="4d90b-103">Fuerza una recolección de elementos no utilizados para la generación especificada.</span><span class="sxs-lookup"><span data-stu-id="4d90b-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d90b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d90b-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d90b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d90b-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="4d90b-106">de Generación que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="4d90b-106">[in] The generation to collect.</span></span> <span data-ttu-id="4d90b-107">Un valor de-1 fuerza una colección de todas las generaciones.</span><span class="sxs-lookup"><span data-stu-id="4d90b-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d90b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d90b-108">Return Value</span></span>  
  
|<span data-ttu-id="4d90b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d90b-109">HRESULT</span></span>|<span data-ttu-id="4d90b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d90b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d90b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d90b-111">S_OK</span></span>|<span data-ttu-id="4d90b-112">`Collect` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d90b-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="4d90b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4d90b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4d90b-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d90b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4d90b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4d90b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4d90b-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4d90b-116">The call timed out.</span></span>|  
|<span data-ttu-id="4d90b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4d90b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4d90b-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4d90b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4d90b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4d90b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4d90b-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="4d90b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4d90b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d90b-121">E_FAIL</span></span>|<span data-ttu-id="4d90b-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4d90b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4d90b-123">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4d90b-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4d90b-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4d90b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d90b-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d90b-125">Remarks</span></span>  
 <span data-ttu-id="4d90b-126">El método `Collect` fuerza al recolector de elementos no utilizados de CLR a realizar una recolección, independientemente de su estado actual.</span><span class="sxs-lookup"><span data-stu-id="4d90b-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d90b-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d90b-127">Requirements</span></span>  
 <span data-ttu-id="4d90b-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d90b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d90b-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4d90b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d90b-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4d90b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d90b-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d90b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d90b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d90b-132">See also</span></span>

- [<span data-ttu-id="4d90b-133">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="4d90b-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="4d90b-134">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="4d90b-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="4d90b-135">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d90b-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="4d90b-136">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d90b-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="4d90b-137">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="4d90b-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="4d90b-138">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4d90b-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="4d90b-139">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="4d90b-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
