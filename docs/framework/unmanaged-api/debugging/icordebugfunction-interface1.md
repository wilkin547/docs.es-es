---
title: ICorDebugFunction Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction
helpviewer_keywords: ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 327ef9f74e94e3b1b20e78eb6a833038b5bfe16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction-interface1"></a><span data-ttu-id="ff23e-102">ICorDebugFunction Interfaz1</span><span class="sxs-lookup"><span data-stu-id="ff23e-102">ICorDebugFunction Interface1</span></span>
<span data-ttu-id="ff23e-103">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="ff23e-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff23e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ff23e-104">Methods</span></span>  
  
|<span data-ttu-id="ff23e-105">Método</span><span class="sxs-lookup"><span data-stu-id="ff23e-105">Method</span></span>|<span data-ttu-id="ff23e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff23e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff23e-107">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="ff23e-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="ff23e-108">Crea un punto de interrupción al principio de esta función.</span><span class="sxs-lookup"><span data-stu-id="ff23e-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="ff23e-109">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="ff23e-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="ff23e-110">Obtiene un objeto ICorDebugClass que representa la clase de de que esta función es un miembro.</span><span class="sxs-lookup"><span data-stu-id="ff23e-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="ff23e-111">GetCurrentVersionNumber (método)</span><span class="sxs-lookup"><span data-stu-id="ff23e-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="ff23e-112">Obtiene el número de versión de la edición más reciente realizada en esta función.</span><span class="sxs-lookup"><span data-stu-id="ff23e-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="ff23e-113">GetILCode (método)</span><span class="sxs-lookup"><span data-stu-id="ff23e-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="ff23e-114">Obtiene el código de lenguaje intermedio (MSIL) de Microsoft para esta función.</span><span class="sxs-lookup"><span data-stu-id="ff23e-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="ff23e-115">GetLocalVarSigToken (método)</span><span class="sxs-lookup"><span data-stu-id="ff23e-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="ff23e-116">Obtiene los metadatos del token para la firma de variable local de la función que está representada por este `ICorDebugFunction` instancia.</span><span class="sxs-lookup"><span data-stu-id="ff23e-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="ff23e-117">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="ff23e-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="ff23e-118">Obtiene el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="ff23e-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="ff23e-119">GetNativeCode (método)</span><span class="sxs-lookup"><span data-stu-id="ff23e-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="ff23e-120">Obtiene el código nativo para esta función.</span><span class="sxs-lookup"><span data-stu-id="ff23e-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="ff23e-121">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="ff23e-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="ff23e-122">Obtiene los metadatos del token para esta función.</span><span class="sxs-lookup"><span data-stu-id="ff23e-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff23e-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff23e-123">Remarks</span></span>  
 <span data-ttu-id="ff23e-124">El `ICorDebugFunction` interfaz no representa una función con parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="ff23e-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="ff23e-125">Por ejemplo, un `ICorDebugFunction` representaría instancia `Func<T>` pero no `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="ff23e-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="ff23e-126">Llame a [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) para obtener los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="ff23e-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="ff23e-127">La relación entre el token de metadatos de un método `mdMethodDef`y un método `ICorDebugFunction` objeto depende de si se permite editar y continuar en la función:</span><span class="sxs-lookup"><span data-stu-id="ff23e-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="ff23e-128">Si no se permite editar y continuar en la función, existe una relación uno a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="ff23e-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="ff23e-129">Es decir, la función tiene una `ICorDebugFunction` objeto y otro `mdMethodDef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="ff23e-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="ff23e-130">Si se permite editar y continuar en la función, existe una relación de varios a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="ff23e-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="ff23e-131">Es decir, la función puede tener muchas instancias de `ICorDebugFunction`, uno para cada versión de la función, pero solo uno `mdMethodDef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="ff23e-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff23e-132">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ff23e-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff23e-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff23e-133">Requirements</span></span>  
 <span data-ttu-id="ff23e-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff23e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff23e-135">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff23e-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff23e-136">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff23e-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff23e-137">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff23e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff23e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff23e-138">See Also</span></span>  
 [<span data-ttu-id="ff23e-139">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ff23e-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
