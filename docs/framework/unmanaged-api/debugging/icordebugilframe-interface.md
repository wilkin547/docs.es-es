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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a40436fcf1485c5d08d175b0396af2b6870c19a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917023"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="d66e4-102">Interfaz ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="d66e4-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="d66e4-103">Representa un marco de pila del código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d66e4-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="d66e4-104">Esta interfaz es una subclase de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="d66e4-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d66e4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d66e4-105">Methods</span></span>  
  
|<span data-ttu-id="d66e4-106">Método</span><span class="sxs-lookup"><span data-stu-id="d66e4-106">Method</span></span>|<span data-ttu-id="d66e4-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d66e4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d66e4-108">CanSetIP (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="d66e4-109">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada.</span><span class="sxs-lookup"><span data-stu-id="d66e4-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="d66e4-110">EnumerateArguments (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="d66e4-111">Obtiene un enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="d66e4-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="d66e4-112">EnumerateLocalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="d66e4-113">Obtiene un enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="d66e4-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="d66e4-114">GetArgument (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="d66e4-115">Obtiene el valor del argumento especificado en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="d66e4-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="d66e4-116">GetIP (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="d66e4-117">Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="d66e4-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="d66e4-118">GetLocalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="d66e4-119">Obtiene el valor de la variable local especificada en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="d66e4-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="d66e4-120">GetStackDepth (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="d66e4-121">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="d66e4-121">Not implemented.</span></span>|  
|[<span data-ttu-id="d66e4-122">GetStackValue (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="d66e4-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="d66e4-123">Not implemented.</span></span>|  
|[<span data-ttu-id="d66e4-124">SetIP (método)</span><span class="sxs-lookup"><span data-stu-id="d66e4-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="d66e4-125">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código MSIL.</span><span class="sxs-lookup"><span data-stu-id="d66e4-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d66e4-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d66e4-126">Remarks</span></span>  
 <span data-ttu-id="d66e4-127">La `ICorDebugILFrame` interfaz es una interfaz de ICorDebugFrame especializada.</span><span class="sxs-lookup"><span data-stu-id="d66e4-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="d66e4-128">Se usa para los marcos de código MSIL o para los marcos compilados Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="d66e4-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="d66e4-129">Los marcos compilados con JIT implementan la `ICorDebugILFrame` interfaz y la interfaz ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="d66e4-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d66e4-130">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d66e4-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d66e4-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d66e4-131">Requirements</span></span>  
 <span data-ttu-id="d66e4-132">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d66e4-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d66e4-133">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="d66e4-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d66e4-134">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d66e4-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d66e4-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d66e4-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d66e4-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d66e4-136">See also</span></span>

- [<span data-ttu-id="d66e4-137">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d66e4-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
