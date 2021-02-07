---
description: 'Más información acerca de: ICorDebugCode (interfaz)'
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
ms.openlocfilehash: ce67c48501783bbe00152f0ba2c224e6e7dde6d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711159"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="5a2c9-103">Interfaz ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="5a2c9-103">ICorDebugCode Interface</span></span>

<span data-ttu-id="5a2c9-104">Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-104">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a2c9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a2c9-105">Methods</span></span>  
  
|<span data-ttu-id="5a2c9-106">Método</span><span class="sxs-lookup"><span data-stu-id="5a2c9-106">Method</span></span>|<span data-ttu-id="5a2c9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a2c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a2c9-108">Método CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5a2c9-108">CreateBreakpoint Method</span></span>](icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="5a2c9-109">Crea un punto de interrupción en el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-109">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="5a2c9-110">Método GetAddress</span><span class="sxs-lookup"><span data-stu-id="5a2c9-110">GetAddress Method</span></span>](icordebugcode-getaddress-method.md)|<span data-ttu-id="5a2c9-111">Obtiene la dirección virtual relativa (RVA) del segmento de código que representa `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-111">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="5a2c9-112">Método GetCode</span><span class="sxs-lookup"><span data-stu-id="5a2c9-112">GetCode Method</span></span>](icordebugcode-getcode-method.md)|<span data-ttu-id="5a2c9-113">Obtiene todo el código para la función especificada, con formato de desensamblado.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-113">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="5a2c9-114">Este método está en desuso; Use [ICorDebugCode2:: getcodechunks (](icordebugcode2-getcodechunks-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-114">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="5a2c9-115">Método GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="5a2c9-115">GetEnCRemapSequencePoints Method</span></span>](icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="5a2c9-116">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-116">Not implemented.</span></span>|  
|[<span data-ttu-id="5a2c9-117">Método GetFunction</span><span class="sxs-lookup"><span data-stu-id="5a2c9-117">GetFunction Method</span></span>](icordebugcode-getfunction-method.md)|<span data-ttu-id="5a2c9-118">Obtiene la "ICorDebugFunction" asociada a este `ICorDebugCode` .</span><span class="sxs-lookup"><span data-stu-id="5a2c9-118">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="5a2c9-119">Método GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="5a2c9-119">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="5a2c9-120">Obtiene una matriz de instancias "COR_DEBUG_IL_TO_NATIVE_MAP" que representan asignaciones de desplazamientos MSIL a desplazamientos nativos.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-120">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="5a2c9-121">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="5a2c9-121">GetSize Method</span></span>](icordebugcode-getsize-method.md)|<span data-ttu-id="5a2c9-122">Obtiene el tamaño, en bytes, del código binario representado por esta instancia de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-122">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="5a2c9-123">GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="5a2c9-123">GetVersionNumber Method</span></span>](icordebugcode-getversionnumber-method.md)|<span data-ttu-id="5a2c9-124">Obtiene el número basado en uno que identifica la versión del código que representa esta instancia de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-124">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="5a2c9-125">Método IsIL</span><span class="sxs-lookup"><span data-stu-id="5a2c9-125">IsIL Method</span></span>](icordebugcode-isil-method.md)|<span data-ttu-id="5a2c9-126">Obtiene un valor que indica si esta instancia de `ICorDebugCode` está compilada en MSIL.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-126">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a2c9-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a2c9-127">Remarks</span></span>  

 <span data-ttu-id="5a2c9-128">`ICorDebugCode` puede representar MSIL o código nativo.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-128">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="5a2c9-129">Un objeto "ICorDebugFunction" que representa el código MSIL puede tener o ninguno de los `ICorDebugCode` objetos asociados.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-129">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="5a2c9-130">Un objeto "ICorDebugFunction" que representa el código nativo puede tener cualquier número de `ICorDebugCode` objetos asociados a él.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-130">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a2c9-131">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5a2c9-131">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a2c9-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a2c9-132">Requirements</span></span>  

 <span data-ttu-id="5a2c9-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a2c9-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a2c9-134">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a2c9-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a2c9-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a2c9-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a2c9-136">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a2c9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a2c9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a2c9-137">See also</span></span>

- [<span data-ttu-id="5a2c9-138">ICorDebugCode3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a2c9-138">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="5a2c9-139">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5a2c9-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
