---
description: 'Más información acerca de: IHostMemoryManager:: VirtualFree (método)'
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
ms.openlocfilehash: 987661ce1b7bfd08f757f53082313b8eb60ff282
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707549"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="55600-103">IHostMemoryManager::VirtualFree (Método)</span><span class="sxs-lookup"><span data-stu-id="55600-103">IHostMemoryManager::VirtualFree Method</span></span>

<span data-ttu-id="55600-104">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="55600-104">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="55600-105">La implementación de Win32 de `VirtualFree` libera, anula la confirmación o libera y anula la confirmación de una región de páginas dentro del espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="55600-105">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55600-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55600-106">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55600-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55600-107">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="55600-108">de Puntero a la dirección base de las páginas de memoria virtual que se van a liberar.</span><span class="sxs-lookup"><span data-stu-id="55600-108">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="55600-109">de Tamaño, en bytes, de la región que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="55600-109">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="55600-110">de Tipo de operación de liberación.</span><span class="sxs-lookup"><span data-stu-id="55600-110">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55600-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="55600-111">Return Value</span></span>  
  
|<span data-ttu-id="55600-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55600-112">HRESULT</span></span>|<span data-ttu-id="55600-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="55600-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55600-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="55600-114">S_OK</span></span>|<span data-ttu-id="55600-115">`VirtualFree` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="55600-115">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="55600-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55600-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55600-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="55600-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55600-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55600-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55600-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="55600-119">The call timed out.</span></span>|  
|<span data-ttu-id="55600-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55600-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55600-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="55600-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55600-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55600-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55600-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="55600-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55600-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55600-124">E_FAIL</span></span>|<span data-ttu-id="55600-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="55600-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55600-126">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="55600-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55600-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="55600-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="55600-128">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="55600-128">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="55600-129">Se intentó liberar memoria que no se asignó a través del host.</span><span class="sxs-lookup"><span data-stu-id="55600-129">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55600-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="55600-130">Remarks</span></span>  

 <span data-ttu-id="55600-131">`VirtualFree` libera las páginas de memoria virtual asociadas al `lpAddress` parámetro a través de una llamada anterior a la función [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="55600-131">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="55600-132">Los intentos de liberar memoria que no se asignaron a través del host deben devolver HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="55600-132">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="55600-133">La semántica es idéntica a la de la implementación de Win32 de `VirtualFree` .</span><span class="sxs-lookup"><span data-stu-id="55600-133">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="55600-134">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="55600-134">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55600-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55600-135">Requirements</span></span>  

 <span data-ttu-id="55600-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55600-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55600-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="55600-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55600-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55600-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55600-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55600-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55600-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="55600-140">See also</span></span>

- [<span data-ttu-id="55600-141">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55600-141">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="55600-142">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55600-142">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
