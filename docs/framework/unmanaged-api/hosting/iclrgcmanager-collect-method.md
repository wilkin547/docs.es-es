---
description: 'Más información sobre: ICLRGCManager:: collect (método)'
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
ms.openlocfilehash: 7c2649f7ce3472c504c1e48a203cf89d4b8508e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746066"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="408d7-103">ICLRGCManager::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="408d7-103">ICLRGCManager::Collect Method</span></span>

<span data-ttu-id="408d7-104">Fuerza una recolección de elementos no utilizados para la generación especificada.</span><span class="sxs-lookup"><span data-stu-id="408d7-104">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="408d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="408d7-105">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="408d7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="408d7-106">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="408d7-107">de Generación que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="408d7-107">[in] The generation to collect.</span></span> <span data-ttu-id="408d7-108">Un valor de-1 fuerza una colección de todas las generaciones.</span><span class="sxs-lookup"><span data-stu-id="408d7-108">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="408d7-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="408d7-109">Return Value</span></span>  
  
|<span data-ttu-id="408d7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="408d7-110">HRESULT</span></span>|<span data-ttu-id="408d7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="408d7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="408d7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="408d7-112">S_OK</span></span>|<span data-ttu-id="408d7-113">`Collect` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="408d7-113">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="408d7-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="408d7-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="408d7-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="408d7-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="408d7-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="408d7-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="408d7-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="408d7-117">The call timed out.</span></span>|  
|<span data-ttu-id="408d7-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="408d7-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="408d7-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="408d7-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="408d7-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="408d7-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="408d7-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="408d7-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="408d7-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="408d7-122">E_FAIL</span></span>|<span data-ttu-id="408d7-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="408d7-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="408d7-124">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="408d7-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="408d7-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="408d7-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="408d7-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="408d7-126">Remarks</span></span>  

 <span data-ttu-id="408d7-127">El `Collect` método obliga al recolector de elementos no utilizados de CLR a realizar una recolección, independientemente de su estado actual.</span><span class="sxs-lookup"><span data-stu-id="408d7-127">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="408d7-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="408d7-128">Requirements</span></span>  

 <span data-ttu-id="408d7-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="408d7-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="408d7-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="408d7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="408d7-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="408d7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="408d7-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="408d7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="408d7-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="408d7-133">See also</span></span>

- [<span data-ttu-id="408d7-134">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="408d7-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="408d7-135">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="408d7-135">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="408d7-136">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="408d7-136">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="408d7-137">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="408d7-137">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="408d7-138">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="408d7-138">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="408d7-139">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="408d7-139">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="408d7-140">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="408d7-140">Hosting</span></span>](index.md)
