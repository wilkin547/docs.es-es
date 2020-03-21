---
title: IHostMAlloc::DebugAlloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178037"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="d8457-102">IHostMAlloc::DebugAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="d8457-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="d8457-103">Solicita que el host asigne la cantidad especificada de memoria del montón y, además, realice un seguimiento de dónde se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="d8457-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8457-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8457-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8457-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8457-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="d8457-106">[en] El tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="d8457-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="d8457-107">[en] Uno de los [eMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valores, que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="d8457-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="d8457-108">[en] El archivo de código del ejecutable que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="d8457-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="d8457-109">[en] El número `pszFileName` de línea en el que se solicitó la asignación.</span><span class="sxs-lookup"><span data-stu-id="d8457-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="d8457-110">[fuera] Un puntero a la memoria asignada, o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d8457-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8457-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8457-111">Return Value</span></span>  
  
|<span data-ttu-id="d8457-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8457-112">HRESULT</span></span>|<span data-ttu-id="d8457-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8457-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8457-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8457-114">S_OK</span></span>|<span data-ttu-id="d8457-115">`DebugAlloc`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="d8457-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="d8457-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8457-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8457-117">El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8457-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8457-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8457-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8457-119">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="d8457-119">The call timed out.</span></span>|  
|<span data-ttu-id="d8457-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8457-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8457-121">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="d8457-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8457-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8457-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8457-123">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="d8457-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8457-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8457-124">E_FAIL</span></span>|<span data-ttu-id="d8457-125">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="d8457-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8457-126">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d8457-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8457-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d8457-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d8457-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d8457-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d8457-129">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="d8457-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8457-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d8457-130">Remarks</span></span>  
 <span data-ttu-id="d8457-131">El CLR obtiene un puntero de interfaz a un [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia mediante una llamada a la [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d8457-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="d8457-132">`DebugAlloc`permite que el tiempo de ejecución obtenga información de archivo de código para su uso durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="d8457-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8457-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8457-133">Requirements</span></span>  
 <span data-ttu-id="d8457-134">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8457-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8457-135">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8457-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8457-136">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8457-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8457-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8457-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8457-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8457-138">See also</span></span>

- [<span data-ttu-id="d8457-139">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8457-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="d8457-140">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8457-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
