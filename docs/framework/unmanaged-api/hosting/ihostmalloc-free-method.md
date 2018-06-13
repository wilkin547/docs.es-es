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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8bd7b16f06433970d1222dbeaa843e187715faa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439002"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="15da3-102">IHostMAlloc::Free (Método)</span><span class="sxs-lookup"><span data-stu-id="15da3-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="15da3-103">Libera la memoria que se asignó mediante el uso de la [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) función.</span><span class="sxs-lookup"><span data-stu-id="15da3-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15da3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15da3-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15da3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15da3-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="15da3-106">[in] Un puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="15da3-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15da3-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15da3-107">Return Value</span></span>  
  
|<span data-ttu-id="15da3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15da3-108">HRESULT</span></span>|<span data-ttu-id="15da3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="15da3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15da3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="15da3-110">S_OK</span></span>|<span data-ttu-id="15da3-111">`Free` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="15da3-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="15da3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15da3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15da3-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="15da3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15da3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15da3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15da3-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="15da3-115">The call timed out.</span></span>|  
|<span data-ttu-id="15da3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15da3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15da3-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="15da3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15da3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15da3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15da3-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="15da3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15da3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15da3-120">E_FAIL</span></span>|<span data-ttu-id="15da3-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="15da3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15da3-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="15da3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15da3-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="15da3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="15da3-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="15da3-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="15da3-125">Se intentó liberar memoria que no se asignó a través del host.</span><span class="sxs-lookup"><span data-stu-id="15da3-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15da3-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15da3-126">Remarks</span></span>  
 <span data-ttu-id="15da3-127">Si el `pMem` parámetro hace referencia a una región de memoria que no se ha asignado mediante una llamada a `Alloc`, el host debe devolver HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="15da3-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15da3-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15da3-128">Requirements</span></span>  
 <span data-ttu-id="15da3-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15da3-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15da3-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15da3-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15da3-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15da3-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15da3-132">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15da3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15da3-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="15da3-133">See Also</span></span>  
 [<span data-ttu-id="15da3-134">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15da3-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="15da3-135">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15da3-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
