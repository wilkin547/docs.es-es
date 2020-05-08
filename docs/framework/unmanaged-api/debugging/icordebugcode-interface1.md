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
ms.openlocfilehash: 3736627e7f42ad9db6699c31a0a618e993eef770
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893467"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="d0c1d-102">Interfaz ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="d0c1d-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="d0c1d-103">Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0c1d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d0c1d-104">Methods</span></span>  
  
|<span data-ttu-id="d0c1d-105">Método</span><span class="sxs-lookup"><span data-stu-id="d0c1d-105">Method</span></span>|<span data-ttu-id="d0c1d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0c1d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0c1d-107">Método CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d0c1d-107">CreateBreakpoint Method</span></span>](icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="d0c1d-108">Crea un punto de interrupción en el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="d0c1d-109">Método GetAddress</span><span class="sxs-lookup"><span data-stu-id="d0c1d-109">GetAddress Method</span></span>](icordebugcode-getaddress-method.md)|<span data-ttu-id="d0c1d-110">Obtiene la dirección virtual relativa (RVA) del segmento de código que representa `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="d0c1d-111">Método GetCode</span><span class="sxs-lookup"><span data-stu-id="d0c1d-111">GetCode Method</span></span>](icordebugcode-getcode-method.md)|<span data-ttu-id="d0c1d-112">Obtiene todo el código para la función especificada, con formato de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="d0c1d-113">Este método está en desuso; Use [ICorDebugCode2:: getcodechunks (](icordebugcode2-getcodechunks-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="d0c1d-114">Método GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="d0c1d-114">GetEnCRemapSequencePoints Method</span></span>](icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="d0c1d-115">No implementado.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-115">Not implemented.</span></span>|  
|[<span data-ttu-id="d0c1d-116">Método GetFunction</span><span class="sxs-lookup"><span data-stu-id="d0c1d-116">GetFunction Method</span></span>](icordebugcode-getfunction-method.md)|<span data-ttu-id="d0c1d-117">Obtiene la "ICorDebugFunction" asociada a este `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="d0c1d-118">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="d0c1d-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="d0c1d-119">Obtiene una matriz de instancias "COR_DEBUG_IL_TO_NATIVE_MAP" que representan asignaciones de desplazamientos MSIL a desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="d0c1d-120">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="d0c1d-120">GetSize Method</span></span>](icordebugcode-getsize-method.md)|<span data-ttu-id="d0c1d-121">Obtiene el tamaño, en bytes, del código binario representado por esta instancia de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="d0c1d-122">GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="d0c1d-122">GetVersionNumber Method</span></span>](icordebugcode-getversionnumber-method.md)|<span data-ttu-id="d0c1d-123">Obtiene el número basado en uno que identifica la versión del código que representa esta instancia de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="d0c1d-124">Método IsIL</span><span class="sxs-lookup"><span data-stu-id="d0c1d-124">IsIL Method</span></span>](icordebugcode-isil-method.md)|<span data-ttu-id="d0c1d-125">Obtiene un valor que indica si esta instancia de `ICorDebugCode` está compilada en MSIL.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0c1d-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d0c1d-126">Remarks</span></span>  
 <span data-ttu-id="d0c1d-127">`ICorDebugCode` puede representar MSIL o código nativo.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="d0c1d-128">Un objeto "ICorDebugFunction" que representa el código MSIL puede tener o ninguno de `ICorDebugCode` los objetos asociados.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="d0c1d-129">Un objeto "ICorDebugFunction" que representa el código nativo puede tener cualquier número `ICorDebugCode` de objetos asociados a él.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0c1d-130">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d0c1d-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0c1d-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0c1d-131">Requirements</span></span>  
 <span data-ttu-id="d0c1d-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0c1d-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0c1d-133">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0c1d-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0c1d-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0c1d-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0c1d-135">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0c1d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c1d-136">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d0c1d-136">See also</span></span>

- [<span data-ttu-id="d0c1d-137">ICorDebugCode3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0c1d-137">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="d0c1d-138">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d0c1d-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
