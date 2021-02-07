---
description: 'Más información acerca de: IHostMemoryManager:: ReleasedVirtualAddressSpace ((método)'
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
ms.openlocfilehash: e67e80018b5002bdf2a50530af9ab057696fff4c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707779"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="74bf6-103">IHostMemoryManager::ReleasedVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="74bf6-103">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>

<span data-ttu-id="74bf6-104">Notifica al host que el Common Language Runtime (CLR) ha terminado de usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="74bf6-104">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74bf6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74bf6-105">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74bf6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74bf6-106">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="74bf6-107">de Puntero a la dirección inicial de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="74bf6-107">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74bf6-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74bf6-108">Remarks</span></span>  

 <span data-ttu-id="74bf6-109">El `ReleasedVirtualAddressSpace` método es un método de devolución de llamada y debe ser implementado por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="74bf6-109">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="74bf6-110">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="74bf6-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74bf6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74bf6-111">Requirements</span></span>  

 <span data-ttu-id="74bf6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74bf6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74bf6-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="74bf6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74bf6-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74bf6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74bf6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74bf6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74bf6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="74bf6-116">See also</span></span>

- [<span data-ttu-id="74bf6-117">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74bf6-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
