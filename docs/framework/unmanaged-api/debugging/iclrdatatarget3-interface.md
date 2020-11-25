---
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
ms.openlocfilehash: 7297bfa5297878dde6867a99029ac88754a05290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723589"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="17747-102">ICLRDataTarget3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17747-102">ICLRDataTarget3 Interface</span></span>

<span data-ttu-id="17747-103">Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a la información de la excepción.</span><span class="sxs-lookup"><span data-stu-id="17747-103">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17747-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="17747-104">Methods</span></span>  
  
|<span data-ttu-id="17747-105">Método</span><span class="sxs-lookup"><span data-stu-id="17747-105">Method</span></span>|<span data-ttu-id="17747-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="17747-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17747-107">Método GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="17747-107">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="17747-108">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de excepciones asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="17747-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="17747-109">Método GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="17747-109">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="17747-110">Los servicios de acceso a datos de CLR llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="17747-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="17747-111">Método GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="17747-111">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="17747-112">Los servicios de acceso a datos de CLR llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="17747-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17747-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17747-113">Remarks</span></span>  

 <span data-ttu-id="17747-114">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="17747-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="17747-115">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="17747-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="17747-116">Puede que el destino no admita la modificación de sus áreas de memoria.</span><span class="sxs-lookup"><span data-stu-id="17747-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17747-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17747-117">Requirements</span></span>  

 <span data-ttu-id="17747-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17747-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17747-119">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="17747-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="17747-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17747-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17747-121">**.NET Framework versiones:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="17747-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17747-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17747-122">See also</span></span>

- [<span data-ttu-id="17747-123">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17747-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="17747-124">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17747-124">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="17747-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="17747-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
