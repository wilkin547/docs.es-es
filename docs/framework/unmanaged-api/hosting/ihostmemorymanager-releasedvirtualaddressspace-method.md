---
title: IHostMemoryManager::ReleasedVirtualAddressSpace (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
ms.openlocfilehash: 8a875d59d270f087ce22079830818a9205309cc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731298"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="13bcc-102">IHostMemoryManager::ReleasedVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="13bcc-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>

<span data-ttu-id="13bcc-103">Notifica al host que el Common Language Runtime (CLR) ha terminado de usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="13bcc-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13bcc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13bcc-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13bcc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13bcc-105">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="13bcc-106">de Puntero a la dirección inicial de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="13bcc-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13bcc-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13bcc-107">Remarks</span></span>  

 <span data-ttu-id="13bcc-108">El `ReleasedVirtualAddressSpace` método es un método de devolución de llamada y debe ser implementado por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="13bcc-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="13bcc-109">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="13bcc-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13bcc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13bcc-110">Requirements</span></span>  

 <span data-ttu-id="13bcc-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13bcc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13bcc-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="13bcc-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13bcc-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13bcc-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13bcc-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13bcc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13bcc-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13bcc-115">See also</span></span>

- [<span data-ttu-id="13bcc-116">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="13bcc-116">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
