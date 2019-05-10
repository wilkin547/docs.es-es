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
ms.openlocfilehash: 550b85474c1ccd7e125549e86df906439caf410e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621496"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="e5c24-102">Interfaz ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="e5c24-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="e5c24-103">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="e5c24-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5c24-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e5c24-104">Methods</span></span>  
  
|<span data-ttu-id="e5c24-105">Método</span><span class="sxs-lookup"><span data-stu-id="e5c24-105">Method</span></span>|<span data-ttu-id="e5c24-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5c24-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5c24-107">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="e5c24-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="e5c24-108">Crea un punto de interrupción al principio de esta función.</span><span class="sxs-lookup"><span data-stu-id="e5c24-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="e5c24-109">GetClass (método)</span><span class="sxs-lookup"><span data-stu-id="e5c24-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="e5c24-110">Obtiene un objeto ICorDebugClass que representa la clase de de que esta función es un miembro.</span><span class="sxs-lookup"><span data-stu-id="e5c24-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="e5c24-111">GetCurrentVersionNumber (método)</span><span class="sxs-lookup"><span data-stu-id="e5c24-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="e5c24-112">Obtiene el número de versión de la edición más reciente realizada en esta función.</span><span class="sxs-lookup"><span data-stu-id="e5c24-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="e5c24-113">GetILCode (método)</span><span class="sxs-lookup"><span data-stu-id="e5c24-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="e5c24-114">Obtiene el código de lenguaje intermedio (MSIL) de Microsoft para esta función.</span><span class="sxs-lookup"><span data-stu-id="e5c24-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="e5c24-115">GetLocalVarSigToken (método)</span><span class="sxs-lookup"><span data-stu-id="e5c24-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="e5c24-116">Obtiene los metadatos de token para la firma de variable local de la función que está representada por este `ICorDebugFunction` instancia.</span><span class="sxs-lookup"><span data-stu-id="e5c24-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="e5c24-117">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="e5c24-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="e5c24-118">Obtiene el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="e5c24-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="e5c24-119">GetNativeCode (método)</span><span class="sxs-lookup"><span data-stu-id="e5c24-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="e5c24-120">Obtiene el código nativo para esta función.</span><span class="sxs-lookup"><span data-stu-id="e5c24-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="e5c24-121">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="e5c24-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="e5c24-122">Obtiene los metadatos de token para esta función.</span><span class="sxs-lookup"><span data-stu-id="e5c24-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5c24-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5c24-123">Remarks</span></span>  
 <span data-ttu-id="e5c24-124">El `ICorDebugFunction` interfaz no representa una función con parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="e5c24-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="e5c24-125">Por ejemplo, un `ICorDebugFunction` representaría instancia `Func<T>` pero no `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="e5c24-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="e5c24-126">Llame a [Icordebugilframe2](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) para obtener los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="e5c24-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="e5c24-127">La relación entre el token de metadatos de un método, `mdMethodDef`y un método `ICorDebugFunction` objeto depende de si se permite editar y continuar en la función:</span><span class="sxs-lookup"><span data-stu-id="e5c24-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="e5c24-128">Si no se permite en la función Editar y continuar, existe una relación uno a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="e5c24-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="e5c24-129">Es decir, la función tiene una `ICorDebugFunction` objeto y `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="e5c24-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="e5c24-130">Si se permite editar y continuar en la función, existe una relación de varios a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="e5c24-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="e5c24-131">Es decir, la función puede tener muchas instancias de `ICorDebugFunction`, uno para cada versión de la función, pero solo uno `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="e5c24-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5c24-132">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e5c24-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c24-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5c24-133">Requirements</span></span>  
 <span data-ttu-id="e5c24-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5c24-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5c24-135">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5c24-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5c24-136">**Biblioteca:**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5c24-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5c24-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5c24-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c24-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5c24-138">See also</span></span>

- [<span data-ttu-id="e5c24-139">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e5c24-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
