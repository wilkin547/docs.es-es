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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed3cb62b56e80a7fe4ea54b43ac9f4a28b8d102
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100254"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="dceeb-102">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dceeb-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="dceeb-103">Proporciona métodos para la interacción con un elemento de destino de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dceeb-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dceeb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dceeb-104">Methods</span></span>  
  
|<span data-ttu-id="dceeb-105">Método</span><span class="sxs-lookup"><span data-stu-id="dceeb-105">Method</span></span>|<span data-ttu-id="dceeb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dceeb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dceeb-107">Método GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="dceeb-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="dceeb-108">Obtiene el identificador de sistema operativo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="dceeb-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="dceeb-109">Método GetImageBase</span><span class="sxs-lookup"><span data-stu-id="dceeb-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="dceeb-110">Obtiene la dirección de memoria de base de la imagen especificada.</span><span class="sxs-lookup"><span data-stu-id="dceeb-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="dceeb-111">Método GetMachineType</span><span class="sxs-lookup"><span data-stu-id="dceeb-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="dceeb-112">Obtiene un identificador para el tipo de conjunto de instrucciones que se está usando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dceeb-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="dceeb-113">Método GetPointerSize</span><span class="sxs-lookup"><span data-stu-id="dceeb-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="dceeb-114">Obtiene el tamaño, en bytes, de un puntero al destino actual.</span><span class="sxs-lookup"><span data-stu-id="dceeb-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="dceeb-115">Método GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="dceeb-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="dceeb-116">Obtiene un puntero al contexto del subproceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="dceeb-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="dceeb-117">Método GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="dceeb-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="dceeb-118">Obtiene un valor en el almacenamiento local de subprocesos (TLS) en el índice especificado para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="dceeb-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="dceeb-119">Método ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="dceeb-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="dceeb-120">Lee datos desde la dirección de memoria virtual especificada en el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="dceeb-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="dceeb-121">Método Request</span><span class="sxs-lookup"><span data-stu-id="dceeb-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="dceeb-122">Llamado por los servicios de acceso a datos de common language runtime (CLR) para solicitar una operación, como se define en la implementación.</span><span class="sxs-lookup"><span data-stu-id="dceeb-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="dceeb-123">Método SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="dceeb-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="dceeb-124">Establece el contexto actual del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dceeb-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="dceeb-125">Método SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="dceeb-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="dceeb-126">Establece un valor en el almacenamiento local de subprocesos (TLS) del subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dceeb-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="dceeb-127">Método WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="dceeb-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="dceeb-128">Escribe datos desde el búfer especificado en la dirección de memoria virtual especificada.</span><span class="sxs-lookup"><span data-stu-id="dceeb-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dceeb-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dceeb-129">Remarks</span></span>  
 <span data-ttu-id="dceeb-130">El cliente de API (es decir, el depurador) debe implementar esta interfaz según corresponda para el elemento de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="dceeb-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="dceeb-131">Por ejemplo, un proceso activo tendría una implementación diferente de la de un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="dceeb-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dceeb-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dceeb-132">Requirements</span></span>  
 <span data-ttu-id="dceeb-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dceeb-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dceeb-134">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="dceeb-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dceeb-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dceeb-135">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="dceeb-136">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dceeb-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dceeb-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="dceeb-137">See also</span></span>

- [<span data-ttu-id="dceeb-138">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dceeb-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="dceeb-139">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dceeb-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
