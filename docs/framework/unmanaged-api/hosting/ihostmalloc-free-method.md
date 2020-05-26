---
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
ms.openlocfilehash: 1dd5ed4c556a5a4d4425a9c0730cebf22ff1785b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804621"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="50236-102">IHostMAlloc::Free (Método)</span><span class="sxs-lookup"><span data-stu-id="50236-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="50236-103">Libera la memoria que se asignó mediante la función de [asignación](ihostmalloc-alloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="50236-103">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50236-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50236-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50236-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50236-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="50236-106">de Puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="50236-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50236-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="50236-107">Return Value</span></span>  
  
|<span data-ttu-id="50236-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50236-108">HRESULT</span></span>|<span data-ttu-id="50236-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="50236-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50236-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="50236-110">S_OK</span></span>|<span data-ttu-id="50236-111">`Free`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="50236-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="50236-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50236-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50236-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="50236-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50236-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50236-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50236-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="50236-115">The call timed out.</span></span>|  
|<span data-ttu-id="50236-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50236-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50236-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="50236-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50236-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50236-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50236-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="50236-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50236-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50236-120">E_FAIL</span></span>|<span data-ttu-id="50236-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="50236-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50236-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="50236-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50236-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="50236-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="50236-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="50236-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="50236-125">Se intentó liberar memoria que no se asignó a través del host.</span><span class="sxs-lookup"><span data-stu-id="50236-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50236-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="50236-126">Remarks</span></span>  
 <span data-ttu-id="50236-127">Si el `pMem` parámetro hace referencia a una región de memoria que no se asignó mediante una llamada a `Alloc` , el host debe devolver HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="50236-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50236-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50236-128">Requirements</span></span>  
 <span data-ttu-id="50236-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50236-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50236-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="50236-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50236-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="50236-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50236-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50236-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50236-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50236-133">See also</span></span>

- [<span data-ttu-id="50236-134">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50236-134">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="50236-135">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50236-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
