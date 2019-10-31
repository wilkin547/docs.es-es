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
ms.openlocfilehash: b53c0bb38922ae8de048c131807eb32f97423d6c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128591"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="dde6f-102">IHostMemoryManager::VirtualFree (Método)</span><span class="sxs-lookup"><span data-stu-id="dde6f-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="dde6f-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dde6f-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="dde6f-104">La implementación de Win32 de `VirtualFree` libera, anula la confirmación o libera y anula la confirmación de una región de páginas dentro del espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="dde6f-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde6f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dde6f-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dde6f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dde6f-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="dde6f-107">de Puntero a la dirección base de las páginas de memoria virtual que se van a liberar.</span><span class="sxs-lookup"><span data-stu-id="dde6f-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="dde6f-108">de Tamaño, en bytes, de la región que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="dde6f-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="dde6f-109">de Tipo de operación de liberación.</span><span class="sxs-lookup"><span data-stu-id="dde6f-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dde6f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dde6f-110">Return Value</span></span>  
  
|<span data-ttu-id="dde6f-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dde6f-111">HRESULT</span></span>|<span data-ttu-id="dde6f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="dde6f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dde6f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="dde6f-113">S_OK</span></span>|<span data-ttu-id="dde6f-114">`VirtualFree` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dde6f-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="dde6f-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dde6f-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dde6f-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="dde6f-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dde6f-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dde6f-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dde6f-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="dde6f-118">The call timed out.</span></span>|  
|<span data-ttu-id="dde6f-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dde6f-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dde6f-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dde6f-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dde6f-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dde6f-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dde6f-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="dde6f-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dde6f-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dde6f-123">E_FAIL</span></span>|<span data-ttu-id="dde6f-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="dde6f-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dde6f-125">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="dde6f-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dde6f-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dde6f-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dde6f-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="dde6f-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="dde6f-128">Se intentó liberar memoria que no se asignó a través del host.</span><span class="sxs-lookup"><span data-stu-id="dde6f-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dde6f-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dde6f-129">Remarks</span></span>  
 <span data-ttu-id="dde6f-130">`VirtualFree` libera las páginas de memoria virtual asociadas al parámetro `lpAddress` a través de una llamada anterior a la función [IHostMemoryManager:: VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dde6f-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="dde6f-131">Los intentos de liberar memoria que no se asignaron a través del host deben devolver HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="dde6f-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="dde6f-132">La semántica es idéntica a la de la implementación de Win32 de `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="dde6f-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="dde6f-133">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="dde6f-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dde6f-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dde6f-134">Requirements</span></span>  
 <span data-ttu-id="dde6f-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dde6f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dde6f-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dde6f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dde6f-137">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dde6f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dde6f-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dde6f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde6f-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="dde6f-139">See also</span></span>

- [<span data-ttu-id="dde6f-140">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dde6f-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="dde6f-141">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dde6f-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
