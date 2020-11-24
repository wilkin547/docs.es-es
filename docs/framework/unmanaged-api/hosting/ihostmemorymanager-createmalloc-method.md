---
title: IHostMemoryManager::CreateMAlloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 79580170d544cd3763992a4bc67fd20e3446bb1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685726"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="3dc2a-102">IHostMemoryManager::CreateMAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="3dc2a-102">IHostMemoryManager::CreateMAlloc Method</span></span>

<span data-ttu-id="3dc2a-103">Obtiene un puntero de interfaz a una instancia de [IHostMAlloc](ihostmalloc-interface.md) que se utiliza para hacer solicitudes de asignación de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-103">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dc2a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3dc2a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3dc2a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3dc2a-105">Parameters</span></span>  

 `dwMallocType`  
 <span data-ttu-id="3dc2a-106">de Combinación de marcas de [MALLOC_TYPE](malloc-type-enumeration.md) que especifica las características de la memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-106">[in] A combination of [MALLOC_TYPE](malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="3dc2a-107">enuncia Puntero a la dirección de una `IHostMAlloc` instancia de proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3dc2a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3dc2a-108">Return Value</span></span>  
  
|<span data-ttu-id="3dc2a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3dc2a-109">HRESULT</span></span>|<span data-ttu-id="3dc2a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dc2a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3dc2a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3dc2a-111">S_OK</span></span>|<span data-ttu-id="3dc2a-112">`CreateMAlloc` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="3dc2a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3dc2a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3dc2a-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3dc2a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3dc2a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3dc2a-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-116">The call timed out.</span></span>|  
|<span data-ttu-id="3dc2a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3dc2a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3dc2a-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3dc2a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3dc2a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3dc2a-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3dc2a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3dc2a-121">E_FAIL</span></span>|<span data-ttu-id="3dc2a-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3dc2a-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3dc2a-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3dc2a-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3dc2a-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3dc2a-126">No había suficiente memoria física disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dc2a-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3dc2a-127">Remarks</span></span>  

 <span data-ttu-id="3dc2a-128">`CreateMAlloc` Devuelve un objeto que permite que CLR realice solicitudes de asignación a través del host en lugar de usar las funciones estándar de Win32.</span><span class="sxs-lookup"><span data-stu-id="3dc2a-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dc2a-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3dc2a-129">Requirements</span></span>  

 <span data-ttu-id="3dc2a-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dc2a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dc2a-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3dc2a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3dc2a-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3dc2a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3dc2a-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dc2a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc2a-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3dc2a-134">See also</span></span>

- [<span data-ttu-id="3dc2a-135">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3dc2a-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="3dc2a-136">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3dc2a-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
