---
title: ICLRDataTarget2 (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d21bced214242866c47f40f392593f3f51cda02f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104720"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="55224-102">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55224-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="55224-103">Una subclase de [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) que se usa la capa de servicios de acceso a datos para manipular las áreas de memoria virtual en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="55224-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55224-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="55224-104">Methods</span></span>  
  
|<span data-ttu-id="55224-105">Método</span><span class="sxs-lookup"><span data-stu-id="55224-105">Method</span></span>|<span data-ttu-id="55224-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="55224-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55224-107">AllocVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="55224-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="55224-108">Asigna memoria en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="55224-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="55224-109">FreeVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="55224-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="55224-110">Libera memoria previamente asignada en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="55224-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55224-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55224-111">Remarks</span></span>  
 <span data-ttu-id="55224-112">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="55224-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="55224-113">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="55224-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="55224-114">Puede que el destino no admita la modificación de sus áreas de memoria.</span><span class="sxs-lookup"><span data-stu-id="55224-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55224-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55224-115">Requirements</span></span>  
 <span data-ttu-id="55224-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55224-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55224-117">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="55224-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="55224-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55224-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55224-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55224-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55224-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="55224-120">See also</span></span>

- [<span data-ttu-id="55224-121">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55224-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="55224-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="55224-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
