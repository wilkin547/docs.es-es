---
title: "IHostMemoryManager::NeedsVirtualAddressSpace (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.NeedsVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62ceb9e5b4d5843b8e2adad344b3ffb662ab3aff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="993a1-102">IHostMemoryManager::NeedsVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="993a1-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="993a1-103">Notifica al host que common language runtime (CLR) se va a intentar utilizar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="993a1-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="993a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="993a1-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="993a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="993a1-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="993a1-106">[in] La dirección inicial de la memoria.</span><span class="sxs-lookup"><span data-stu-id="993a1-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="993a1-107">[in] El tamaño, en bytes, de la memoria.</span><span class="sxs-lookup"><span data-stu-id="993a1-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="993a1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="993a1-108">Remarks</span></span>  
 <span data-ttu-id="993a1-109">El `NeedsVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="993a1-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="993a1-110">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="993a1-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="993a1-111">Si el host no desea que el CLR para utilizar la memoria especificada, puede devolver un HRESULT de E_OUTOFMEMORY.</span><span class="sxs-lookup"><span data-stu-id="993a1-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="993a1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="993a1-112">Requirements</span></span>  
 <span data-ttu-id="993a1-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="993a1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="993a1-114">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="993a1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="993a1-115">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="993a1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="993a1-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="993a1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="993a1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="993a1-117">See Also</span></span>  
 [<span data-ttu-id="993a1-118">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="993a1-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
