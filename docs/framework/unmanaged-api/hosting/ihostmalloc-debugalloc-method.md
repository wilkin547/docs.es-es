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
ms.openlocfilehash: a2a752f23ed64795f9208b9101c21bc585d5f431
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136814"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="1132b-102">IHostMAlloc::DebugAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="1132b-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="1132b-103">Solicita que el host asigne la cantidad de memoria especificada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="1132b-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1132b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1132b-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1132b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1132b-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="1132b-106">de Tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="1132b-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="1132b-107">de Uno de los valores de [ememorycriticallevel (](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) , que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="1132b-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="1132b-108">de El archivo de código del ejecutable que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="1132b-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="1132b-109">de El número de línea en `pszFileName` donde se solicitó la asignación.</span><span class="sxs-lookup"><span data-stu-id="1132b-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="1132b-110">enuncia Puntero a la memoria asignada o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1132b-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1132b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1132b-111">Return Value</span></span>  
  
|<span data-ttu-id="1132b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1132b-112">HRESULT</span></span>|<span data-ttu-id="1132b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1132b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1132b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1132b-114">S_OK</span></span>|<span data-ttu-id="1132b-115">`DebugAlloc` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1132b-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="1132b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1132b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1132b-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1132b-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1132b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1132b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1132b-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1132b-119">The call timed out.</span></span>|  
|<span data-ttu-id="1132b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1132b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1132b-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1132b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1132b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1132b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1132b-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1132b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1132b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1132b-124">E_FAIL</span></span>|<span data-ttu-id="1132b-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1132b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1132b-126">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1132b-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1132b-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1132b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1132b-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1132b-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1132b-129">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="1132b-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1132b-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1132b-130">Remarks</span></span>  
 <span data-ttu-id="1132b-131">CLR obtiene un puntero de interfaz a una instancia de [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) llamando al método [IHostMemoryManager:: CreateMAlloc (](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1132b-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="1132b-132">`DebugAlloc` permite al motor en tiempo de ejecución obtener información del archivo de código para su uso durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="1132b-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1132b-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1132b-133">Requirements</span></span>  
 <span data-ttu-id="1132b-134">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1132b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1132b-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1132b-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1132b-136">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1132b-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1132b-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1132b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1132b-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="1132b-138">See also</span></span>

- [<span data-ttu-id="1132b-139">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1132b-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="1132b-140">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1132b-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
