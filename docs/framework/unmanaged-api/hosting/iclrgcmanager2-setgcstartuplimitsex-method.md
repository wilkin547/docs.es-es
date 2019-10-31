---
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
ms.openlocfilehash: 77de550cd3fb614e03f8028707c3cbf914734910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141090"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="5ff93-102">ICLRGCManager2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="5ff93-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="5ff93-103">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5ff93-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ff93-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ff93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ff93-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="5ff93-106">de Tamaño especificado de un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5ff93-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="5ff93-107">El tamaño mínimo del segmento es 4 MB.</span><span class="sxs-lookup"><span data-stu-id="5ff93-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="5ff93-108">Los segmentos se pueden aumentar en incrementos de 1 MB o más.</span><span class="sxs-lookup"><span data-stu-id="5ff93-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="5ff93-109">de Tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="5ff93-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="5ff93-110">El tamaño mínimo de la generación 0 es 64 KB.</span><span class="sxs-lookup"><span data-stu-id="5ff93-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ff93-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5ff93-111">Return Value</span></span>  
  
|<span data-ttu-id="5ff93-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ff93-112">HRESULT</span></span>|<span data-ttu-id="5ff93-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ff93-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ff93-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ff93-114">S_OK</span></span>|<span data-ttu-id="5ff93-115">`SetGCStartupLimitsEx` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ff93-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="5ff93-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5ff93-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5ff93-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ff93-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5ff93-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5ff93-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5ff93-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5ff93-119">The call timed out.</span></span>|  
|<span data-ttu-id="5ff93-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5ff93-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5ff93-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5ff93-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5ff93-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5ff93-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5ff93-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5ff93-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5ff93-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ff93-124">E_FAIL</span></span>|<span data-ttu-id="5ff93-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5ff93-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5ff93-126">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5ff93-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5ff93-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5ff93-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ff93-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ff93-128">Remarks</span></span>  
 <span data-ttu-id="5ff93-129">Los valores que `SetGCStartupLimitsEx` establece solo se pueden especificar antes de que se inicie el host.</span><span class="sxs-lookup"><span data-stu-id="5ff93-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="5ff93-130">Las llamadas posteriores a `SetGCStartupLimitsEx` se omiten.</span><span class="sxs-lookup"><span data-stu-id="5ff93-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="5ff93-131">Para establecer cualquiera de los parámetros sin afectar al otro, especifique 0 (cero) para el parámetro que no quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="5ff93-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff93-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ff93-132">Requirements</span></span>  
 <span data-ttu-id="5ff93-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ff93-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff93-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5ff93-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ff93-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5ff93-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ff93-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff93-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff93-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ff93-137">See also</span></span>

- [<span data-ttu-id="5ff93-138">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="5ff93-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="5ff93-139">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="5ff93-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="5ff93-140">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ff93-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5ff93-141">ICLRGCManager2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ff93-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
