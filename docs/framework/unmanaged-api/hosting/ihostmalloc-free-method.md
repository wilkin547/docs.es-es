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
ms.openlocfilehash: f7ae4e4cbb757edea242c57720baeb70ced5c428
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192053"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="311be-102">IHostMAlloc::Free (Método)</span><span class="sxs-lookup"><span data-stu-id="311be-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="311be-103">Libera la memoria que se asignó mediante la función de [asignación](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="311be-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="311be-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="311be-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="311be-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="311be-106">de Puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="311be-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="311be-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="311be-107">Return Value</span></span>  
  
|<span data-ttu-id="311be-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="311be-108">HRESULT</span></span>|<span data-ttu-id="311be-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="311be-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="311be-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="311be-110">S_OK</span></span>|<span data-ttu-id="311be-111">`Free` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="311be-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="311be-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="311be-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="311be-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="311be-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="311be-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="311be-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="311be-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="311be-115">The call timed out.</span></span>|  
|<span data-ttu-id="311be-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="311be-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="311be-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="311be-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="311be-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="311be-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="311be-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="311be-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="311be-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="311be-120">E_FAIL</span></span>|<span data-ttu-id="311be-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="311be-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="311be-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="311be-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="311be-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="311be-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="311be-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="311be-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="311be-125">Se intentó liberar memoria que no se asignó a través del host.</span><span class="sxs-lookup"><span data-stu-id="311be-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="311be-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="311be-126">Remarks</span></span>  
 <span data-ttu-id="311be-127">Si el parámetro `pMem` hace referencia a una región de memoria que no se asignó mediante una llamada a `Alloc`, el host debe devolver HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="311be-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="311be-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="311be-128">Requirements</span></span>  
 <span data-ttu-id="311be-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="311be-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="311be-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="311be-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="311be-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="311be-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="311be-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="311be-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311be-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="311be-133">See also</span></span>

- [<span data-ttu-id="311be-134">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="311be-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="311be-135">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="311be-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
