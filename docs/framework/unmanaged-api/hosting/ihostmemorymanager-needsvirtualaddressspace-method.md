---
description: 'Más información acerca de: IHostMemoryManager:: Needsvirtualaddressspace ((método)'
title: IHostMemoryManager::NeedsVirtualAddressSpace (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
ms.openlocfilehash: 95d4128decffc82fdcb198155b48a31420f71220
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707792"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="e9c0b-103">IHostMemoryManager::NeedsVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="e9c0b-103">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>

<span data-ttu-id="e9c0b-104">Notifica al host que el Common Language Runtime (CLR) intentará usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="e9c0b-104">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c0b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9c0b-105">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9c0b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9c0b-106">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="e9c0b-107">de Dirección inicial de la memoria.</span><span class="sxs-lookup"><span data-stu-id="e9c0b-107">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="e9c0b-108">de Tamaño, en bytes, de la memoria.</span><span class="sxs-lookup"><span data-stu-id="e9c0b-108">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9c0b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e9c0b-109">Remarks</span></span>  

 <span data-ttu-id="e9c0b-110">El `NeedsVirtualAddressSpace` método es un método de devolución de llamada y debe ser implementado por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="e9c0b-110">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="e9c0b-111">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="e9c0b-111">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="e9c0b-112">Si el host no desea que CLR use la memoria especificada, puede devolver una E_OUTOFMEMORY HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e9c0b-112">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9c0b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9c0b-113">Requirements</span></span>  

 <span data-ttu-id="e9c0b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9c0b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c0b-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e9c0b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9c0b-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9c0b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9c0b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9c0b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c0b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9c0b-118">See also</span></span>

- [<span data-ttu-id="e9c0b-119">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9c0b-119">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
