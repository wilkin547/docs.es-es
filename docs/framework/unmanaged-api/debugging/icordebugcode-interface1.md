---
title: Interfaz ICorDebugCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75cc8ea9d88dda42362f50b519864b1a78e1a64b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960790"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="1b1cc-102">Interfaz ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="1b1cc-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="1b1cc-103">Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b1cc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1b1cc-104">Methods</span></span>  
  
|<span data-ttu-id="1b1cc-105">Método</span><span class="sxs-lookup"><span data-stu-id="1b1cc-105">Method</span></span>|<span data-ttu-id="1b1cc-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1b1cc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b1cc-107">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="1b1cc-108">Crea un punto de interrupción en el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="1b1cc-109">GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="1b1cc-110">Obtiene la dirección virtual relativa (RVA) del segmento de código que representa `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="1b1cc-111">GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="1b1cc-112">Obtiene todo el código para la función especificada, con formato de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="1b1cc-113">Este método está en desuso; Use [ICorDebugCode2:: getcodechunks (](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="1b1cc-114">GetEnCRemapSequencePoints (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="1b1cc-115">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-115">Not implemented.</span></span>|  
|[<span data-ttu-id="1b1cc-116">GetFunction (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="1b1cc-117">Obtiene la "ICorDebugFunction" asociada a este `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="1b1cc-118">GetILToNativeMapping (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="1b1cc-119">Obtiene una matriz de instancias de "COR_DEBUG_IL_TO_NATIVE_MAP" que representan asignaciones de desplazamientos de MSIL a desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="1b1cc-120">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="1b1cc-121">Obtiene el tamaño, en bytes, del código binario representado por esta instancia de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="1b1cc-122">GetVersionNumber (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="1b1cc-123">Obtiene el número basado en uno que identifica la versión del código que representa esta instancia de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="1b1cc-124">IsIL (método)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="1b1cc-125">Obtiene un valor que indica si esta instancia de `ICorDebugCode` está compilada en MSIL.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b1cc-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b1cc-126">Remarks</span></span>  
 <span data-ttu-id="1b1cc-127">`ICorDebugCode` puede representar MSIL o código nativo.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="1b1cc-128">Un objeto "ICorDebugFunction" que representa el código MSIL puede tener o `ICorDebugCode` ninguno de los objetos asociados.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="1b1cc-129">Un objeto "ICorDebugFunction" que representa el código nativo puede tener cualquier número `ICorDebugCode` de objetos asociados a él.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b1cc-130">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1b1cc-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b1cc-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b1cc-131">Requirements</span></span>  
 <span data-ttu-id="1b1cc-132">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b1cc-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b1cc-133">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="1b1cc-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b1cc-134">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b1cc-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b1cc-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b1cc-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1cc-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b1cc-136">See also</span></span>

- [<span data-ttu-id="1b1cc-137">ICorDebugCode3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b1cc-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="1b1cc-138">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1b1cc-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
