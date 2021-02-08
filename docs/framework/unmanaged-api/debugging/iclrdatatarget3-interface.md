---
description: 'Más información acerca de: interfaz ICLRDataTarget3'
title: ICLRDataTarget3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
ms.openlocfilehash: deea609298563e60897f9bedab9fb1e175dc7b73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794794"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="c008e-103">ICLRDataTarget3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c008e-103">ICLRDataTarget3 Interface</span></span>

<span data-ttu-id="c008e-104">Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a la información de la excepción.</span><span class="sxs-lookup"><span data-stu-id="c008e-104">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c008e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c008e-105">Methods</span></span>  
  
|<span data-ttu-id="c008e-106">Método</span><span class="sxs-lookup"><span data-stu-id="c008e-106">Method</span></span>|<span data-ttu-id="c008e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c008e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c008e-108">Método GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="c008e-108">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="c008e-109">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de excepciones asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c008e-109">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="c008e-110">Método GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="c008e-110">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="c008e-111">Los servicios de acceso a datos de CLR llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c008e-111">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="c008e-112">Método GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="c008e-112">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="c008e-113">Los servicios de acceso a datos de CLR llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="c008e-113">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c008e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c008e-114">Remarks</span></span>  

 <span data-ttu-id="c008e-115">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="c008e-115">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="c008e-116">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="c008e-116">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="c008e-117">Puede que el destino no admita la modificación de sus áreas de memoria.</span><span class="sxs-lookup"><span data-stu-id="c008e-117">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c008e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c008e-118">Requirements</span></span>  

 <span data-ttu-id="c008e-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c008e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c008e-120">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="c008e-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c008e-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c008e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c008e-122">**.NET Framework versiones:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c008e-122">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c008e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c008e-123">See also</span></span>

- [<span data-ttu-id="c008e-124">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c008e-124">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="c008e-125">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c008e-125">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="c008e-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c008e-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
