---
title: IHostMemoryManager::AcquiredVirtualAddressSpace (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4675c34bfe8d1d79c184c43e5f7f5dd3a03be6a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201005"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="62ea4-102">IHostMemoryManager::AcquiredVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="62ea4-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="62ea4-103">Notifica al host que common language runtime (CLR) ha adquirido la memoria especificada desde el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="62ea4-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62ea4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62ea4-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62ea4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62ea4-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="62ea4-106">[in] La dirección inicial de la memoria.</span><span class="sxs-lookup"><span data-stu-id="62ea4-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="62ea4-107">[in] El tamaño, en bytes, de la memoria.</span><span class="sxs-lookup"><span data-stu-id="62ea4-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62ea4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62ea4-108">Remarks</span></span>  
 <span data-ttu-id="62ea4-109">El `AcquiredVirtualAddressSpace` es un método de devolución de llamada de método y debe ser implementada por el sistema de escritura de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="62ea4-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="62ea4-110">Se llama a CLR.</span><span class="sxs-lookup"><span data-stu-id="62ea4-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62ea4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62ea4-111">Requirements</span></span>  
 <span data-ttu-id="62ea4-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62ea4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62ea4-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62ea4-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62ea4-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62ea4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="62ea4-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="62ea4-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="62ea4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="62ea4-116">See also</span></span>

- [<span data-ttu-id="62ea4-117">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62ea4-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
