---
description: 'Más información acerca de: IHostMemoryManager:: AcquiredVirtualAddressSpace ((método)'
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
ms.openlocfilehash: 70424c5bf907cfc3fb2e8951464335323f9331f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707922"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="98741-103">IHostMemoryManager::AcquiredVirtualAddressSpace (Método)</span><span class="sxs-lookup"><span data-stu-id="98741-103">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>

<span data-ttu-id="98741-104">Notifica al host que el Common Language Runtime (CLR) ha adquirido la memoria especificada del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="98741-104">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98741-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98741-105">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98741-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98741-106">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="98741-107">de Dirección inicial de la memoria.</span><span class="sxs-lookup"><span data-stu-id="98741-107">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="98741-108">de Tamaño, en bytes, de la memoria.</span><span class="sxs-lookup"><span data-stu-id="98741-108">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98741-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="98741-109">Remarks</span></span>  

 <span data-ttu-id="98741-110">El `AcquiredVirtualAddressSpace` método es un método de devolución de llamada y debe ser implementado por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="98741-110">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="98741-111">Lo llama el CLR.</span><span class="sxs-lookup"><span data-stu-id="98741-111">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98741-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98741-112">Requirements</span></span>  

 <span data-ttu-id="98741-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98741-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98741-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="98741-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98741-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98741-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98741-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98741-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98741-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="98741-117">See also</span></span>

- [<span data-ttu-id="98741-118">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98741-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
