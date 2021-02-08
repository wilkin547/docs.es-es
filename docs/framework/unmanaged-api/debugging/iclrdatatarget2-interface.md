---
description: 'Más información acerca de: interfaz ICLRDataTarget2'
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
ms.openlocfilehash: 9ba6d11ea043d3b6ba85544b47e063f585854af8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794850"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="a8d37-103">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8d37-103">ICLRDataTarget2 Interface</span></span>

<span data-ttu-id="a8d37-104">Una subclase de [ICLRDataTarget](iclrdatatarget-interface.md) utilizada por el nivel de servicios de acceso a datos para manipular regiones de memoria virtual en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="a8d37-104">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8d37-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a8d37-105">Methods</span></span>  
  
|<span data-ttu-id="a8d37-106">Método</span><span class="sxs-lookup"><span data-stu-id="a8d37-106">Method</span></span>|<span data-ttu-id="a8d37-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8d37-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8d37-108">Método AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="a8d37-108">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="a8d37-109">Asigna memoria en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="a8d37-109">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="a8d37-110">Método FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="a8d37-110">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="a8d37-111">Libera memoria previamente asignada en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="a8d37-111">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8d37-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a8d37-112">Remarks</span></span>  

 <span data-ttu-id="a8d37-113">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="a8d37-113">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="a8d37-114">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="a8d37-114">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="a8d37-115">Puede que el destino no admita la modificación de sus áreas de memoria.</span><span class="sxs-lookup"><span data-stu-id="a8d37-115">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8d37-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8d37-116">Requirements</span></span>  

 <span data-ttu-id="a8d37-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8d37-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8d37-118">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="a8d37-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a8d37-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8d37-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8d37-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8d37-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8d37-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8d37-121">See also</span></span>

- [<span data-ttu-id="a8d37-122">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8d37-122">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="a8d37-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a8d37-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
