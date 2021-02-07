---
description: 'Más información acerca de: IHostMAlloc::D método ebugAlloc'
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
ms.openlocfilehash: f94ff0d6cc1e25daee12c67c38167f7f14829510
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708221"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="1b089-103">IHostMAlloc::DebugAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="1b089-103">IHostMAlloc::DebugAlloc Method</span></span>

<span data-ttu-id="1b089-104">Solicita que el host asigne la cantidad de memoria especificada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="1b089-104">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b089-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b089-105">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b089-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b089-106">Parameters</span></span>  

 `cbSize`  
 <span data-ttu-id="1b089-107">de Tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="1b089-107">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="1b089-108">de Uno de los valores de [ememorycriticallevel (](ememorycriticallevel-enumeration.md) , que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="1b089-108">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="1b089-109">de El archivo de código del ejecutable que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="1b089-109">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="1b089-110">de El número de línea en el `pszFileName` que se solicitó la asignación.</span><span class="sxs-lookup"><span data-stu-id="1b089-110">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="1b089-111">enuncia Puntero a la memoria asignada o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1b089-111">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b089-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1b089-112">Return Value</span></span>  
  
|<span data-ttu-id="1b089-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b089-113">HRESULT</span></span>|<span data-ttu-id="1b089-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b089-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b089-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b089-115">S_OK</span></span>|<span data-ttu-id="1b089-116">`DebugAlloc` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1b089-116">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="1b089-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b089-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b089-118">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1b089-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b089-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b089-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b089-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1b089-120">The call timed out.</span></span>|  
|<span data-ttu-id="1b089-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b089-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b089-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1b089-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b089-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b089-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b089-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1b089-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b089-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b089-125">E_FAIL</span></span>|<span data-ttu-id="1b089-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1b089-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b089-127">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1b089-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b089-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1b089-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1b089-129">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1b089-129">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1b089-130">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="1b089-130">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b089-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1b089-131">Remarks</span></span>  

 <span data-ttu-id="1b089-132">CLR obtiene un puntero de interfaz a una instancia de [IHostMAlloc](ihostmalloc-interface.md) llamando al método [IHostMemoryManager:: CreateMAlloc (](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1b089-132">The CLR gets an interface pointer to an [IHostMalloc](ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="1b089-133">`DebugAlloc` permite al motor en tiempo de ejecución obtener información del archivo de código para su uso durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="1b089-133">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b089-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b089-134">Requirements</span></span>  

 <span data-ttu-id="1b089-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b089-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b089-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1b089-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b089-137">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b089-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b089-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b089-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b089-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b089-139">See also</span></span>

- [<span data-ttu-id="1b089-140">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b089-140">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="1b089-141">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b089-141">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
