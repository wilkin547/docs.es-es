---
title: ICLRDataTarget2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8d8dc7aad35e38b2f9d3b5fb48dacbe1d22bd34
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="c1a88-102">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1a88-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="c1a88-103">Una subclase de [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) que se usa la capa de servicios de acceso a datos para manipular las áreas de memoria virtual en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c1a88-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1a88-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c1a88-104">Methods</span></span>  
  
|<span data-ttu-id="c1a88-105">Método</span><span class="sxs-lookup"><span data-stu-id="c1a88-105">Method</span></span>|<span data-ttu-id="c1a88-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1a88-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1a88-107">AllocVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="c1a88-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="c1a88-108">Asigna memoria en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c1a88-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="c1a88-109">FreeVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="c1a88-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="c1a88-110">Libera memoria previamente asignada en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c1a88-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1a88-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1a88-111">Remarks</span></span>  
 <span data-ttu-id="c1a88-112">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="c1a88-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="c1a88-113">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="c1a88-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="c1a88-114">Puede que el destino no admita la modificación de sus áreas de memoria.</span><span class="sxs-lookup"><span data-stu-id="c1a88-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1a88-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1a88-115">Requirements</span></span>  
 <span data-ttu-id="c1a88-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1a88-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1a88-117">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c1a88-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c1a88-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1a88-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1a88-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1a88-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a88-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1a88-120">See Also</span></span>  
 [<span data-ttu-id="c1a88-121">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1a88-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="c1a88-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c1a88-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
