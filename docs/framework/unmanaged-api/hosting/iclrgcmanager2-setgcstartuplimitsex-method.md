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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 276f83ff95d4f63f9a26807fe2601c68e3f6b063
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574916"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="80b44-102">ICLRGCManager2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="80b44-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="80b44-103">Establece el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="80b44-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b44-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80b44-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80b44-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80b44-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="80b44-106">[in] El tamaño especificado de un segmento de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="80b44-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="80b44-107">El tamaño mínimo de segmento es 4 MB.</span><span class="sxs-lookup"><span data-stu-id="80b44-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="80b44-108">Segmentos pueden ser mayor en incrementos de 1 MB o superior.</span><span class="sxs-lookup"><span data-stu-id="80b44-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="80b44-109">[in] El tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="80b44-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="80b44-110">El tamaño mínimo de generación 0 es 64 KB.</span><span class="sxs-lookup"><span data-stu-id="80b44-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80b44-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80b44-111">Return Value</span></span>  
  
|<span data-ttu-id="80b44-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80b44-112">HRESULT</span></span>|<span data-ttu-id="80b44-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="80b44-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80b44-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="80b44-114">S_OK</span></span>|<span data-ttu-id="80b44-115">`SetGCStartupLimitsEx` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="80b44-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="80b44-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="80b44-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="80b44-117">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="80b44-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="80b44-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="80b44-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="80b44-119">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="80b44-119">The call timed out.</span></span>|  
|<span data-ttu-id="80b44-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="80b44-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="80b44-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="80b44-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="80b44-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="80b44-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="80b44-123">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="80b44-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="80b44-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80b44-124">E_FAIL</span></span>|<span data-ttu-id="80b44-125">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="80b44-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="80b44-126">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="80b44-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="80b44-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="80b44-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80b44-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80b44-128">Remarks</span></span>  
 <span data-ttu-id="80b44-129">Los valores que `SetGCStartupLimitsEx` se pueden especificar conjuntos antes de iniciar el host.</span><span class="sxs-lookup"><span data-stu-id="80b44-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="80b44-130">Las llamadas posteriores a `SetGCStartupLimitsEx` se omiten.</span><span class="sxs-lookup"><span data-stu-id="80b44-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="80b44-131">Para establecer cualquiera de los parámetros sin que afecte a la otra, especifique 0 (cero) para el parámetro que no desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="80b44-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80b44-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80b44-132">Requirements</span></span>  
 <span data-ttu-id="80b44-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80b44-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80b44-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80b44-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80b44-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80b44-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80b44-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80b44-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b44-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="80b44-137">See also</span></span>
- [<span data-ttu-id="80b44-138">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="80b44-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="80b44-139">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="80b44-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="80b44-140">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80b44-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="80b44-141">ICLRGCManager2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80b44-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
