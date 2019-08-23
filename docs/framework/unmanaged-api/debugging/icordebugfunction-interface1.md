---
title: Interfaz ICorDebugFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae65c59efe1d925b5e058e8664d1e093fdfec875
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917202"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="db0ce-102">Interfaz ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="db0ce-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="db0ce-103">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="db0ce-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db0ce-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="db0ce-104">Methods</span></span>  
  
|<span data-ttu-id="db0ce-105">Método</span><span class="sxs-lookup"><span data-stu-id="db0ce-105">Method</span></span>|<span data-ttu-id="db0ce-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="db0ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db0ce-107">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="db0ce-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="db0ce-108">Crea un punto de interrupción al principio de esta función.</span><span class="sxs-lookup"><span data-stu-id="db0ce-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="db0ce-109">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="db0ce-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="db0ce-110">Obtiene un objeto ICorDebugClass que representa la clase de la que es miembro esta función.</span><span class="sxs-lookup"><span data-stu-id="db0ce-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="db0ce-111">GetCurrentVersionNumber (método)</span><span class="sxs-lookup"><span data-stu-id="db0ce-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="db0ce-112">Obtiene el número de versión de la edición más reciente realizada en esta función.</span><span class="sxs-lookup"><span data-stu-id="db0ce-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="db0ce-113">GetILCode (método)</span><span class="sxs-lookup"><span data-stu-id="db0ce-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="db0ce-114">Obtiene el código del lenguaje intermedio de Microsoft (MSIL) de esta función.</span><span class="sxs-lookup"><span data-stu-id="db0ce-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="db0ce-115">GetLocalVarSigToken (método)</span><span class="sxs-lookup"><span data-stu-id="db0ce-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="db0ce-116">Obtiene el símbolo (token) de metadatos de la firma de variable local de la `ICorDebugFunction` función representada por esta instancia.</span><span class="sxs-lookup"><span data-stu-id="db0ce-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="db0ce-117">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="db0ce-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="db0ce-118">Obtiene el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="db0ce-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="db0ce-119">GetNativeCode (método)</span><span class="sxs-lookup"><span data-stu-id="db0ce-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="db0ce-120">Obtiene el código nativo de esta función.</span><span class="sxs-lookup"><span data-stu-id="db0ce-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="db0ce-121">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="db0ce-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="db0ce-122">Obtiene el símbolo (token) de metadatos de esta función.</span><span class="sxs-lookup"><span data-stu-id="db0ce-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db0ce-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db0ce-123">Remarks</span></span>  
 <span data-ttu-id="db0ce-124">La `ICorDebugFunction` interfaz no representa una función con parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="db0ce-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="db0ce-125">Por ejemplo, una `ICorDebugFunction` instancia de representaría `Func<string>` `Func<T>` pero no.</span><span class="sxs-lookup"><span data-stu-id="db0ce-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="db0ce-126">Llame a [ICorDebugILFrame2:: EnumerateTypeParameters (](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) para obtener los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="db0ce-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="db0ce-127">La relación entre el token de metadatos de `mdMethodDef`un método,, y `ICorDebugFunction` el objeto de un método depende de si se permite editar y continuar en la función:</span><span class="sxs-lookup"><span data-stu-id="db0ce-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="db0ce-128">Si no se permite editar y continuar en la función, existe una relación uno a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="db0ce-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="db0ce-129">Es decir, la función tiene un `ICorDebugFunction` objeto y un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="db0ce-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="db0ce-130">Si se permite editar y continuar en la función, existe una relación de varios a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="db0ce-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="db0ce-131">Es decir, la función puede tener muchas instancias de `ICorDebugFunction`, una por cada versión de la función, pero solo un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="db0ce-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db0ce-132">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="db0ce-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db0ce-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db0ce-133">Requirements</span></span>  
 <span data-ttu-id="db0ce-134">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db0ce-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db0ce-135">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="db0ce-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db0ce-136">**Biblioteca**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db0ce-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="db0ce-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db0ce-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db0ce-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="db0ce-138">See also</span></span>

- [<span data-ttu-id="db0ce-139">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="db0ce-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
