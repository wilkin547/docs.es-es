---
title: "IHostMemoryManager::AcquiredVirtualAddressSpace (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.AcquiredVirtualAddressSpace
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480dba9257c34af2cd1bc11aba4a07a4fbbe1162
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="990ac-102">IHostMemoryManager::AcquiredVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="990ac-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="990ac-103">Notifica al host que common language runtime (CLR) ha adquirido la memoria especificada del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="990ac-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="990ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="990ac-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="990ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="990ac-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="990ac-106">[in] La dirección inicial de la memoria.</span><span class="sxs-lookup"><span data-stu-id="990ac-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="990ac-107">[in] El tamaño, en bytes, de la memoria.</span><span class="sxs-lookup"><span data-stu-id="990ac-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="990ac-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="990ac-108">Remarks</span></span>  
 <span data-ttu-id="990ac-109">El `AcquiredVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="990ac-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="990ac-110">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="990ac-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="990ac-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="990ac-111">Requirements</span></span>  
 <span data-ttu-id="990ac-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="990ac-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="990ac-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="990ac-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="990ac-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="990ac-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="990ac-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="990ac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="990ac-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="990ac-116">See Also</span></span>  
 [<span data-ttu-id="990ac-117">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="990ac-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
