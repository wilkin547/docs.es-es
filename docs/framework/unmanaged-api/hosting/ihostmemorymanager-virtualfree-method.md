---
title: IHostMemoryManager::VirtualFree (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03cac2b8433d6491d1fa474a0d4064ef4e260d6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993231"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="ff1d2-102">IHostMemoryManager::VirtualFree (Método)</span><span class="sxs-lookup"><span data-stu-id="ff1d2-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="ff1d2-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="ff1d2-104">La implementación de Win32 de `VirtualFree` libera, anula el registro, o si libera y anula una región de páginas dentro del espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff1d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff1d2-105">Syntax</span></span>  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff1d2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff1d2-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="ff1d2-107">[in] Un puntero a la dirección base de las páginas de memoria virtual que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="ff1d2-108">[in] El tamaño, en bytes, de la región que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="ff1d2-109">[in] El tipo de operación de liberación.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff1d2-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff1d2-110">Return Value</span></span>  
  
|<span data-ttu-id="ff1d2-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff1d2-111">HRESULT</span></span>|<span data-ttu-id="ff1d2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff1d2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff1d2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff1d2-113">S_OK</span></span>|<span data-ttu-id="ff1d2-114">`VirtualFree` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="ff1d2-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ff1d2-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ff1d2-116">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ff1d2-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ff1d2-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ff1d2-118">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-118">The call timed out.</span></span>|  
|<span data-ttu-id="ff1d2-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff1d2-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ff1d2-120">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ff1d2-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ff1d2-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ff1d2-122">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ff1d2-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ff1d2-123">E_FAIL</span></span>|<span data-ttu-id="ff1d2-124">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ff1d2-125">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ff1d2-126">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ff1d2-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ff1d2-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ff1d2-128">Se ha intentado para liberar memoria que no se ha asignado a través del host.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff1d2-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff1d2-129">Remarks</span></span>  
 <span data-ttu-id="ff1d2-130">`VirtualFree` libera las páginas de memoria virtual asociadas con el `lpAddress` parámetro a través de una llamada anterior a la [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) función.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="ff1d2-131">Intenta liberar memoria que no se ha asignado a través del host debe devolver HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="ff1d2-132">La semántica es idéntica a la de la implementación de Win32 de `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="ff1d2-133">Para obtener más información, consulte la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="ff1d2-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff1d2-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff1d2-134">Requirements</span></span>  
 <span data-ttu-id="ff1d2-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff1d2-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff1d2-136">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff1d2-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff1d2-137">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff1d2-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff1d2-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff1d2-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff1d2-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff1d2-139">See also</span></span>

- [<span data-ttu-id="ff1d2-140">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff1d2-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="ff1d2-141">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff1d2-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
