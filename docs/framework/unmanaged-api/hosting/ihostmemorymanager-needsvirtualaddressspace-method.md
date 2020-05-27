---
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
ms.openlocfilehash: bb13c7329c558aa92ec65237aa8a9963c82fe1dc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804512"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="86433-102">IHostMemoryManager::NeedsVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="86433-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="86433-103">Notifica al host que el Common Language Runtime (CLR) intentará usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="86433-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86433-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86433-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86433-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86433-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="86433-106">de Dirección inicial de la memoria.</span><span class="sxs-lookup"><span data-stu-id="86433-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="86433-107">de Tamaño, en bytes, de la memoria.</span><span class="sxs-lookup"><span data-stu-id="86433-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86433-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86433-108">Remarks</span></span>  
 <span data-ttu-id="86433-109">El `NeedsVirtualAddressSpace` método es un método de devolución de llamada y debe ser implementado por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="86433-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="86433-110">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="86433-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="86433-111">Si el host no desea que CLR use la memoria especificada, puede devolver una E_OUTOFMEMORY HRESULT.</span><span class="sxs-lookup"><span data-stu-id="86433-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86433-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86433-112">Requirements</span></span>  
 <span data-ttu-id="86433-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86433-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86433-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="86433-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86433-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="86433-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86433-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86433-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86433-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86433-117">See also</span></span>

- [<span data-ttu-id="86433-118">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86433-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
