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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74e106e17c0f0e5702927c4599fb143fb3554ce3
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "55065952"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="25aa5-102">ICLRDataTarget3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25aa5-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="25aa5-103">Una subclase de [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) que proporciona acceso a información de excepción.</span><span class="sxs-lookup"><span data-stu-id="25aa5-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25aa5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="25aa5-104">Methods</span></span>  
  
|<span data-ttu-id="25aa5-105">Método</span><span class="sxs-lookup"><span data-stu-id="25aa5-105">Method</span></span>|<span data-ttu-id="25aa5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="25aa5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25aa5-107">GetExceptionRecord (método)</span><span class="sxs-lookup"><span data-stu-id="25aa5-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="25aa5-108">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de excepciones asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="25aa5-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="25aa5-109">GetExceptionContextRecord (método)</span><span class="sxs-lookup"><span data-stu-id="25aa5-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="25aa5-110">Los servicios de acceso a datos de CLR llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="25aa5-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="25aa5-111">GetExceptionThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="25aa5-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="25aa5-112">Los servicios de acceso a datos de CLR llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="25aa5-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25aa5-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25aa5-113">Remarks</span></span>  
 <span data-ttu-id="25aa5-114">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="25aa5-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="25aa5-115">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="25aa5-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="25aa5-116">Puede que el destino no admita la modificación de sus áreas de memoria.</span><span class="sxs-lookup"><span data-stu-id="25aa5-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25aa5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25aa5-117">Requirements</span></span>  
 <span data-ttu-id="25aa5-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25aa5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25aa5-119">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="25aa5-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="25aa5-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25aa5-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25aa5-121">**Versiones de .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="25aa5-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25aa5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="25aa5-122">See also</span></span>
- [<span data-ttu-id="25aa5-123">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25aa5-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="25aa5-124">ICLRDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25aa5-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="25aa5-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="25aa5-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
