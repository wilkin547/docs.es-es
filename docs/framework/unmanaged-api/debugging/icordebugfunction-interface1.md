---
description: 'Más información sobre: ICorDebugFunction (interfaz)'
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
ms.openlocfilehash: 835625341889e89e15ceb66ca71531cf7b8311c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692399"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="5ae52-103">Interfaz ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="5ae52-103">ICorDebugFunction Interface</span></span>

<span data-ttu-id="5ae52-104">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="5ae52-104">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ae52-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5ae52-105">Methods</span></span>  
  
|<span data-ttu-id="5ae52-106">Método</span><span class="sxs-lookup"><span data-stu-id="5ae52-106">Method</span></span>|<span data-ttu-id="5ae52-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ae52-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ae52-108">Método CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5ae52-108">CreateBreakpoint Method</span></span>](icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="5ae52-109">Crea un punto de interrupción al principio de esta función.</span><span class="sxs-lookup"><span data-stu-id="5ae52-109">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="5ae52-110">Método GetClass</span><span class="sxs-lookup"><span data-stu-id="5ae52-110">GetClass Method</span></span>](icordebugfunction-getclass-method.md)|<span data-ttu-id="5ae52-111">Obtiene un objeto ICorDebugClass que representa la clase de la que es miembro esta función.</span><span class="sxs-lookup"><span data-stu-id="5ae52-111">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="5ae52-112">Método GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="5ae52-112">GetCurrentVersionNumber Method</span></span>](icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="5ae52-113">Obtiene el número de versión de la edición más reciente realizada en esta función.</span><span class="sxs-lookup"><span data-stu-id="5ae52-113">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="5ae52-114">Método GetILCode</span><span class="sxs-lookup"><span data-stu-id="5ae52-114">GetILCode Method</span></span>](icordebugfunction-getilcode-method.md)|<span data-ttu-id="5ae52-115">Obtiene el código del lenguaje intermedio de Microsoft (MSIL) de esta función.</span><span class="sxs-lookup"><span data-stu-id="5ae52-115">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="5ae52-116">GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="5ae52-116">GetLocalVarSigToken Method</span></span>](icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="5ae52-117">Obtiene el símbolo (token) de metadatos de la firma de variable local de la función representada por esta `ICorDebugFunction` instancia.</span><span class="sxs-lookup"><span data-stu-id="5ae52-117">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="5ae52-118">GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="5ae52-118">GetModule Method</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="5ae52-119">Obtiene el módulo en el que se define esta función.</span><span class="sxs-lookup"><span data-stu-id="5ae52-119">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="5ae52-120">Método GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="5ae52-120">GetNativeCode Method</span></span>](icordebugfunction-getnativecode-method.md)|<span data-ttu-id="5ae52-121">Obtiene el código nativo de esta función.</span><span class="sxs-lookup"><span data-stu-id="5ae52-121">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="5ae52-122">GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="5ae52-122">GetToken Method</span></span>](icordebugfunction-gettoken-method.md)|<span data-ttu-id="5ae52-123">Obtiene el símbolo (token) de metadatos de esta función.</span><span class="sxs-lookup"><span data-stu-id="5ae52-123">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ae52-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5ae52-124">Remarks</span></span>  

 <span data-ttu-id="5ae52-125">La `ICorDebugFunction` interfaz no representa una función con parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5ae52-125">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="5ae52-126">Por ejemplo, una `ICorDebugFunction` instancia de representaría `Func<T>` pero no `Func<string>` .</span><span class="sxs-lookup"><span data-stu-id="5ae52-126">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="5ae52-127">Llame a [ICorDebugILFrame2:: EnumerateTypeParameters (](icordebugilframe2-enumeratetypeparameters-method.md) para obtener los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5ae52-127">Call [ICorDebugILFrame2::EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="5ae52-128">La relación entre el token de metadatos de un método, `mdMethodDef` , y el objeto de un método `ICorDebugFunction` depende de si se permite editar y continuar en la función:</span><span class="sxs-lookup"><span data-stu-id="5ae52-128">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="5ae52-129">Si no se permite editar y continuar en la función, existe una relación uno a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="5ae52-129">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="5ae52-130">Es decir, la función tiene un `ICorDebugFunction` objeto y un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="5ae52-130">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="5ae52-131">Si se permite editar y continuar en la función, existe una relación de varios a uno entre el `ICorDebugFunction` objeto y el `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="5ae52-131">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="5ae52-132">Es decir, la función puede tener muchas instancias de `ICorDebugFunction` , una por cada versión de la función, pero solo un `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="5ae52-132">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ae52-133">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5ae52-133">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ae52-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ae52-134">Requirements</span></span>  

 <span data-ttu-id="5ae52-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ae52-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ae52-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ae52-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ae52-137">**Biblioteca:**  CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5ae52-137">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ae52-138">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ae52-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae52-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ae52-139">See also</span></span>

- [<span data-ttu-id="5ae52-140">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5ae52-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
