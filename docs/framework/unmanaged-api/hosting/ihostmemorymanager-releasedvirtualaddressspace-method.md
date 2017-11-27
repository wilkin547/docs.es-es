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
ms.openlocfilehash: c0f2588c34429366794fcfb30c6d6e7038814506
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="f79fc-102">IHostMemoryManager::ReleasedVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="f79fc-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="f79fc-103">Notifica al host que common language runtime (CLR) ha terminado de utilizar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="f79fc-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f79fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f79fc-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f79fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f79fc-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="f79fc-106">[in] Puntero a la dirección inicial de la memoria se libera.</span><span class="sxs-lookup"><span data-stu-id="f79fc-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f79fc-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f79fc-107">Remarks</span></span>  
 <span data-ttu-id="f79fc-108">El `ReleasedVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="f79fc-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="f79fc-109">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="f79fc-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f79fc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f79fc-110">Requirements</span></span>  
 <span data-ttu-id="f79fc-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f79fc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f79fc-112">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f79fc-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f79fc-113">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f79fc-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f79fc-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f79fc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f79fc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f79fc-115">See Also</span></span>  
 [<span data-ttu-id="f79fc-116">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f79fc-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
