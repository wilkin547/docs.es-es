---
title: ICLRGCManager::SetGCStartupLimits (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
ms.openlocfilehash: 0dce86a12ed3e93983ee62620fa0ddf7dfbc48f5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616949"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="35319-102">ICLRGCManager::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="35319-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="35319-103">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="35319-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="35319-104">A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 en valores mayores que mediante `DWORD` el método [iclrgcmanager2 (:: setgcstartuplimitsex (](iclrgcmanager2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35319-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35319-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35319-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35319-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35319-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="35319-107">de Tamaño especificado de un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="35319-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="35319-108">El tamaño mínimo del segmento es 4 MB.</span><span class="sxs-lookup"><span data-stu-id="35319-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="35319-109">Los segmentos se pueden aumentar en incrementos de 1 MB o más.</span><span class="sxs-lookup"><span data-stu-id="35319-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="35319-110">de Tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="35319-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="35319-111">El tamaño mínimo de la generación 0 es 64 KB.</span><span class="sxs-lookup"><span data-stu-id="35319-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35319-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="35319-112">Return Value</span></span>  
  
|<span data-ttu-id="35319-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35319-113">HRESULT</span></span>|<span data-ttu-id="35319-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="35319-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35319-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="35319-115">S_OK</span></span>|<span data-ttu-id="35319-116">`SetGCStartupLimits`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="35319-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="35319-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35319-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35319-118">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="35319-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35319-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35319-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35319-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="35319-120">The call timed out.</span></span>|  
|<span data-ttu-id="35319-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35319-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35319-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="35319-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35319-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35319-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35319-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="35319-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35319-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35319-125">E_FAIL</span></span>|<span data-ttu-id="35319-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="35319-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="35319-127">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="35319-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35319-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="35319-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35319-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35319-129">Remarks</span></span>  
 <span data-ttu-id="35319-130">Los valores que `SetGCStartupLimits` establece solo se pueden especificar una vez.</span><span class="sxs-lookup"><span data-stu-id="35319-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="35319-131">Las llamadas posteriores a `SetGCStartupLimits` se omiten.</span><span class="sxs-lookup"><span data-stu-id="35319-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35319-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35319-132">Requirements</span></span>  
 <span data-ttu-id="35319-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35319-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35319-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="35319-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35319-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="35319-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35319-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35319-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35319-137">Consulta también</span><span class="sxs-lookup"><span data-stu-id="35319-137">See also</span></span>

- [<span data-ttu-id="35319-138">Administración de memoria automática</span><span class="sxs-lookup"><span data-stu-id="35319-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="35319-139">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="35319-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="35319-140">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35319-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="35319-141">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35319-141">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
