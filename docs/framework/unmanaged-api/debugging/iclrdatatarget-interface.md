---
description: 'Más información acerca de: ICLRDataTarget (interfaz)'
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
ms.openlocfilehash: f24760f638705a1bde7e055069cbc3a18a0896fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738226"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="dd951-103">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd951-103">ICLRDataTarget Interface</span></span>

<span data-ttu-id="dd951-104">Proporciona métodos para la interacción con un elemento de destino del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dd951-104">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd951-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dd951-105">Methods</span></span>  
  
|<span data-ttu-id="dd951-106">Método</span><span class="sxs-lookup"><span data-stu-id="dd951-106">Method</span></span>|<span data-ttu-id="dd951-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd951-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd951-108">Método GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="dd951-108">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="dd951-109">Obtiene el identificador del sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="dd951-109">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="dd951-110">Método GetImageBase</span><span class="sxs-lookup"><span data-stu-id="dd951-110">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="dd951-111">Obtiene la dirección de memoria base para la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="dd951-111">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="dd951-112">Método GetMachineType</span><span class="sxs-lookup"><span data-stu-id="dd951-112">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="dd951-113">Obtiene un identificador para el tipo de conjunto de instrucciones que está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dd951-113">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="dd951-114">Método GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="dd951-114">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="dd951-115">Obtiene el tamaño, en bytes, de un puntero al destino actual.</span><span class="sxs-lookup"><span data-stu-id="dd951-115">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="dd951-116">GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="dd951-116">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="dd951-117">Obtiene un puntero al contexto del subproceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="dd951-117">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="dd951-118">Método GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="dd951-118">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="dd951-119">Obtiene un valor en el almacenamiento local de subprocesos (TLS) en el índice especificado para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="dd951-119">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="dd951-120">Método ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="dd951-120">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="dd951-121">Lee datos de la dirección de memoria virtual especificada en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="dd951-121">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="dd951-122">Método de solicitud</span><span class="sxs-lookup"><span data-stu-id="dd951-122">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="dd951-123">Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.</span><span class="sxs-lookup"><span data-stu-id="dd951-123">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="dd951-124">Método SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="dd951-124">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="dd951-125">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dd951-125">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="dd951-126">Método SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="dd951-126">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="dd951-127">Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dd951-127">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="dd951-128">Método WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="dd951-128">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="dd951-129">Escribe datos del búfer especificado en la dirección de memoria virtual especificada.</span><span class="sxs-lookup"><span data-stu-id="dd951-129">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd951-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dd951-130">Remarks</span></span>  

 <span data-ttu-id="dd951-131">El cliente de API (es decir, el depurador) debe implementar esta interfaz según corresponda para el elemento de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="dd951-131">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="dd951-132">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="dd951-132">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd951-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd951-133">Requirements</span></span>  

 <span data-ttu-id="dd951-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd951-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd951-135">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="dd951-135">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dd951-136">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd951-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd951-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd951-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd951-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd951-138">See also</span></span>

- [<span data-ttu-id="dd951-139">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd951-139">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="dd951-140">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dd951-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
