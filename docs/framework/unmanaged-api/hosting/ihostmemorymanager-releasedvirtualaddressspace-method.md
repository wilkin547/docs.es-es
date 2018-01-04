---
title: "IHostMemoryManager::ReleasedVirtualAddressSpace (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.ReleasedVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6db2868405aadb5879241e12128c6db40c0a5c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="20e5c-102">IHostMemoryManager::ReleasedVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="20e5c-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="20e5c-103">Notifica al host que common language runtime (CLR) ha terminado de utilizar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="20e5c-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20e5c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20e5c-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20e5c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20e5c-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="20e5c-106">[in] Puntero a la dirección inicial de la memoria se libera.</span><span class="sxs-lookup"><span data-stu-id="20e5c-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20e5c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20e5c-107">Remarks</span></span>  
 <span data-ttu-id="20e5c-108">El `ReleasedVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="20e5c-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="20e5c-109">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="20e5c-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20e5c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20e5c-110">Requirements</span></span>  
 <span data-ttu-id="20e5c-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20e5c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20e5c-112">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20e5c-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20e5c-113">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20e5c-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20e5c-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20e5c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e5c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="20e5c-115">See Also</span></span>  
 [<span data-ttu-id="20e5c-116">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20e5c-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
