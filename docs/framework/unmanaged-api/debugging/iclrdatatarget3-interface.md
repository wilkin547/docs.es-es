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
ms.openlocfilehash: 54d6535e2b2c4761eb3c67a990c62f2c311cf133
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406869"
---
# <a name="iclrdatatarget3-interface"></a><span data-ttu-id="aa7c2-102">ICLRDataTarget3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa7c2-102">ICLRDataTarget3 Interface</span></span>
<span data-ttu-id="aa7c2-103">Una subclase de [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) que proporciona acceso a información de excepción.</span><span class="sxs-lookup"><span data-stu-id="aa7c2-103">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa7c2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="aa7c2-104">Methods</span></span>  
  
|<span data-ttu-id="aa7c2-105">Método</span><span class="sxs-lookup"><span data-stu-id="aa7c2-105">Method</span></span>|<span data-ttu-id="aa7c2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa7c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa7c2-107">GetExceptionRecord (método)</span><span class="sxs-lookup"><span data-stu-id="aa7c2-107">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|<span data-ttu-id="aa7c2-108">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de excepciones asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="aa7c2-108">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span>|  
|[<span data-ttu-id="aa7c2-109">GetExceptionContextRecord (método)</span><span class="sxs-lookup"><span data-stu-id="aa7c2-109">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|<span data-ttu-id="aa7c2-110">Los servicios de acceso a datos de CLR llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="aa7c2-110">Called by the CLR data access services to retrieve the context record associated with the target process.</span></span>|  
|[<span data-ttu-id="aa7c2-111">GetExceptionThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="aa7c2-111">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|<span data-ttu-id="aa7c2-112">Los servicios de acceso a datos de CLR llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="aa7c2-112">Called by the CLR data access services to get the ID of the thread that threw the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa7c2-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa7c2-113">Remarks</span></span>  
 <span data-ttu-id="aa7c2-114">El cliente API (es decir, el depurador) debe implementar esta interfaz según corresponda para el proceso de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="aa7c2-114">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="aa7c2-115">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="aa7c2-115">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="aa7c2-116">Puede que el destino no admita la modificación de sus áreas de memoria.</span><span class="sxs-lookup"><span data-stu-id="aa7c2-116">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa7c2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa7c2-117">Requirements</span></span>  
 <span data-ttu-id="aa7c2-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa7c2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa7c2-119">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="aa7c2-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="aa7c2-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa7c2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa7c2-121">**Versiones de .NET framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa7c2-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa7c2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa7c2-122">See Also</span></span>  
 [<span data-ttu-id="aa7c2-123">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa7c2-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [<span data-ttu-id="aa7c2-124">ICLRDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa7c2-124">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="aa7c2-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="aa7c2-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
