---
title: ICLRDataTarget (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 2b5c99e40aabdbc654bdc612729b2756e3ef5bb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793713"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="c6fbb-102">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="c6fbb-103">Proporciona métodos para la interacción con un elemento de destino del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c6fbb-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6fbb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c6fbb-104">Methods</span></span>  
  
|<span data-ttu-id="c6fbb-105">Método</span><span class="sxs-lookup"><span data-stu-id="c6fbb-105">Method</span></span>|<span data-ttu-id="c6fbb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6fbb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6fbb-107">GetCurrentThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="c6fbb-108">Obtiene el identificador del sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="c6fbb-109">GetImageBase (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="c6fbb-110">Obtiene la dirección de memoria base para la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="c6fbb-111">GetMachineType (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="c6fbb-112">Obtiene un identificador para el tipo de conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="c6fbb-113">GetPointerSize (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="c6fbb-114">Obtiene el tamaño, en bytes, de un puntero al destino actual.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="c6fbb-115">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="c6fbb-116">Obtiene un puntero al contexto del subproceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="c6fbb-117">GetTLSValue (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="c6fbb-118">Obtiene un valor en el almacenamiento local de subprocesos (TLS) en el índice especificado para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="c6fbb-119">ReadVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="c6fbb-120">Lee datos de la dirección de memoria virtual especificada en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="c6fbb-121">Método de solicitud</span><span class="sxs-lookup"><span data-stu-id="c6fbb-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="c6fbb-122">Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="c6fbb-123">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="c6fbb-124">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="c6fbb-125">SetTLSValue (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="c6fbb-126">Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="c6fbb-127">WriteVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="c6fbb-128">Escribe datos del búfer especificado en la dirección de memoria virtual especificada.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6fbb-129">Notas</span><span class="sxs-lookup"><span data-stu-id="c6fbb-129">Remarks</span></span>  
 <span data-ttu-id="c6fbb-130">El cliente de API (es decir, el depurador) debe implementar esta interfaz según corresponda para el elemento de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="c6fbb-131">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="c6fbb-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6fbb-132">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c6fbb-132">Requirements</span></span>  
 <span data-ttu-id="c6fbb-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6fbb-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6fbb-134">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="c6fbb-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c6fbb-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6fbb-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6fbb-136">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6fbb-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6fbb-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6fbb-137">See also</span></span>

- [<span data-ttu-id="c6fbb-138">ICLRDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6fbb-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="c6fbb-139">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c6fbb-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
