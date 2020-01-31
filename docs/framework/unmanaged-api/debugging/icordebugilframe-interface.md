---
title: Interfaz ICorDebugILFrame
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
ms.openlocfilehash: 7a27b8ec512498c7bf817aca36267c37d8070a4c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788579"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="48fd5-102">Interfaz ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="48fd5-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="48fd5-103">Representa un marco de pila del código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="48fd5-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="48fd5-104">Esta interfaz es una subclase de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="48fd5-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48fd5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="48fd5-105">Methods</span></span>  
  
|<span data-ttu-id="48fd5-106">Método</span><span class="sxs-lookup"><span data-stu-id="48fd5-106">Method</span></span>|<span data-ttu-id="48fd5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="48fd5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48fd5-108">CanSetIP (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-108">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="48fd5-109">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada.</span><span class="sxs-lookup"><span data-stu-id="48fd5-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="48fd5-110">EnumerateArguments (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-110">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="48fd5-111">Obtiene un enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="48fd5-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="48fd5-112">EnumerateLocalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-112">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="48fd5-113">Obtiene un enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="48fd5-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="48fd5-114">GetArgument (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-114">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="48fd5-115">Obtiene el valor del argumento especificado en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="48fd5-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="48fd5-116">GetIP (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-116">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="48fd5-117">Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="48fd5-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="48fd5-118">GetLocalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-118">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="48fd5-119">Obtiene el valor de la variable local especificada en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="48fd5-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="48fd5-120">GetStackDepth (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-120">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="48fd5-121">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="48fd5-121">Not implemented.</span></span>|  
|[<span data-ttu-id="48fd5-122">GetStackValue (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-122">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="48fd5-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="48fd5-123">Not implemented.</span></span>|  
|[<span data-ttu-id="48fd5-124">SetIP (método)</span><span class="sxs-lookup"><span data-stu-id="48fd5-124">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="48fd5-125">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código MSIL.</span><span class="sxs-lookup"><span data-stu-id="48fd5-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48fd5-126">Notas</span><span class="sxs-lookup"><span data-stu-id="48fd5-126">Remarks</span></span>  
 <span data-ttu-id="48fd5-127">La interfaz de `ICorDebugILFrame` es una interfaz de ICorDebugFrame especializada.</span><span class="sxs-lookup"><span data-stu-id="48fd5-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="48fd5-128">Se usa para los marcos de código MSIL o para los marcos compilados Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="48fd5-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="48fd5-129">Los marcos compilados JIT implementan tanto la interfaz `ICorDebugILFrame` como la interfaz ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="48fd5-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48fd5-130">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="48fd5-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48fd5-131">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="48fd5-131">Requirements</span></span>  
 <span data-ttu-id="48fd5-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48fd5-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48fd5-133">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48fd5-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48fd5-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48fd5-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48fd5-135">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48fd5-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48fd5-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="48fd5-136">See also</span></span>

- [<span data-ttu-id="48fd5-137">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="48fd5-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
