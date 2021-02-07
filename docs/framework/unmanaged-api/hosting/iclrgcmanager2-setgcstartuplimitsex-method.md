---
description: 'Más información sobre: Iclrgcmanager2 (:: Setgcstartuplimitsex ((método)'
title: ICLRGCManager2::SetGCStartupLimitsEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
ms.openlocfilehash: 2a4801d2f6255f5f84e0a4bae7a1886689ee8dc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689244"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="72a2b-103">ICLRGCManager2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="72a2b-103">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>

<span data-ttu-id="72a2b-104">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="72a2b-104">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72a2b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72a2b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72a2b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72a2b-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="72a2b-107">de Tamaño especificado de un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="72a2b-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="72a2b-108">El tamaño mínimo del segmento es 4 MB.</span><span class="sxs-lookup"><span data-stu-id="72a2b-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="72a2b-109">Los segmentos se pueden aumentar en incrementos de 1 MB o más.</span><span class="sxs-lookup"><span data-stu-id="72a2b-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="72a2b-110">de Tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="72a2b-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="72a2b-111">El tamaño mínimo de la generación 0 es 64 KB.</span><span class="sxs-lookup"><span data-stu-id="72a2b-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72a2b-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72a2b-112">Return Value</span></span>  
  
|<span data-ttu-id="72a2b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72a2b-113">HRESULT</span></span>|<span data-ttu-id="72a2b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="72a2b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72a2b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="72a2b-115">S_OK</span></span>|<span data-ttu-id="72a2b-116">`SetGCStartupLimitsEx` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="72a2b-116">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="72a2b-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="72a2b-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="72a2b-118">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="72a2b-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="72a2b-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="72a2b-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="72a2b-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="72a2b-120">The call timed out.</span></span>|  
|<span data-ttu-id="72a2b-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="72a2b-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="72a2b-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="72a2b-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="72a2b-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="72a2b-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="72a2b-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="72a2b-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="72a2b-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="72a2b-125">E_FAIL</span></span>|<span data-ttu-id="72a2b-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="72a2b-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="72a2b-127">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="72a2b-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="72a2b-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="72a2b-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72a2b-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="72a2b-129">Remarks</span></span>  

 <span data-ttu-id="72a2b-130">Los valores que `SetGCStartupLimitsEx` establece se pueden especificar solo antes de que se inicie el host.</span><span class="sxs-lookup"><span data-stu-id="72a2b-130">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="72a2b-131">Las llamadas posteriores a `SetGCStartupLimitsEx` se omiten.</span><span class="sxs-lookup"><span data-stu-id="72a2b-131">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="72a2b-132">Para establecer cualquiera de los parámetros sin afectar al otro, especifique 0 (cero) para el parámetro que no quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="72a2b-132">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72a2b-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72a2b-133">Requirements</span></span>  

 <span data-ttu-id="72a2b-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72a2b-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72a2b-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="72a2b-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72a2b-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72a2b-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72a2b-137">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72a2b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72a2b-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="72a2b-138">See also</span></span>

- [<span data-ttu-id="72a2b-139">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="72a2b-139">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="72a2b-140">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="72a2b-140">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="72a2b-141">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="72a2b-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="72a2b-142">ICLRGCManager2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="72a2b-142">ICLRGCManager2 Interface</span></span>](iclrgcmanager2-interface.md)
