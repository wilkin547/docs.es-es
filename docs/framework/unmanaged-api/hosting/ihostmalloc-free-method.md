---
description: 'Más información acerca de: IHostMAlloc:: Free (método)'
title: IHostMAlloc::Free (Método)
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
ms.openlocfilehash: 097e2e95b6dfb9d6a1bae68f9e0455a96383159e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708208"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="4b345-103">IHostMAlloc::Free (Método)</span><span class="sxs-lookup"><span data-stu-id="4b345-103">IHostMAlloc::Free Method</span></span>

<span data-ttu-id="4b345-104">Libera la memoria que se asignó mediante la función de [asignación](ihostmalloc-alloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4b345-104">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b345-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b345-105">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b345-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b345-106">Parameters</span></span>  

 `pMem`  
 <span data-ttu-id="4b345-107">de Puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="4b345-107">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b345-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4b345-108">Return Value</span></span>  
  
|<span data-ttu-id="4b345-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b345-109">HRESULT</span></span>|<span data-ttu-id="4b345-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b345-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b345-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b345-111">S_OK</span></span>|<span data-ttu-id="4b345-112">`Free` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b345-112">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="4b345-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4b345-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4b345-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b345-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4b345-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4b345-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4b345-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4b345-116">The call timed out.</span></span>|  
|<span data-ttu-id="4b345-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4b345-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4b345-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4b345-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4b345-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4b345-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4b345-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="4b345-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4b345-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b345-121">E_FAIL</span></span>|<span data-ttu-id="4b345-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4b345-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b345-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4b345-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4b345-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4b345-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4b345-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="4b345-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="4b345-126">Se intentó liberar memoria que no se asignó a través del host.</span><span class="sxs-lookup"><span data-stu-id="4b345-126">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b345-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b345-127">Remarks</span></span>  

 <span data-ttu-id="4b345-128">Si el `pMem` parámetro hace referencia a una región de memoria que no se asignó mediante una llamada a `Alloc` , el host debe devolver HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="4b345-128">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b345-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b345-129">Requirements</span></span>  

 <span data-ttu-id="4b345-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b345-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b345-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4b345-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b345-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b345-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b345-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b345-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b345-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b345-134">See also</span></span>

- [<span data-ttu-id="4b345-135">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b345-135">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="4b345-136">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b345-136">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
