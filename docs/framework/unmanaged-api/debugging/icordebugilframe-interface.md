---
title: ICorDebugILFrame (Interfaz)
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
ms.openlocfilehash: 01c247f838f66d1a77831755126a5a1f56870c1e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095142"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="a0f4a-102">ICorDebugILFrame (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="a0f4a-103">Representa un marco de pila del código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="a0f4a-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="a0f4a-104">Esta interfaz es una subclase de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0f4a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a0f4a-105">Methods</span></span>  
  
|<span data-ttu-id="a0f4a-106">Método</span><span class="sxs-lookup"><span data-stu-id="a0f4a-106">Method</span></span>|<span data-ttu-id="a0f4a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0f4a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0f4a-108">CanSetIP (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="a0f4a-109">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="a0f4a-110">EnumerateArguments (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="a0f4a-111">Obtiene un enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="a0f4a-112">EnumerateLocalVariables (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="a0f4a-113">Obtiene un enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="a0f4a-114">GetArgument (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="a0f4a-115">Obtiene el valor del argumento especificado en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="a0f4a-116">GetIP (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="a0f4a-117">Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="a0f4a-118">GetLocalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="a0f4a-119">Obtiene el valor de la variable local especificada en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="a0f4a-120">GetStackDepth (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="a0f4a-121">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-121">Not implemented.</span></span>|  
|[<span data-ttu-id="a0f4a-122">GetStackValue (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="a0f4a-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-123">Not implemented.</span></span>|  
|[<span data-ttu-id="a0f4a-124">SetIP (método)</span><span class="sxs-lookup"><span data-stu-id="a0f4a-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="a0f4a-125">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código MSIL.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0f4a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0f4a-126">Remarks</span></span>  
 <span data-ttu-id="a0f4a-127">La interfaz de `ICorDebugILFrame` es una interfaz de ICorDebugFrame especializada.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="a0f4a-128">Se usa para los marcos de código MSIL o para los marcos compilados Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="a0f4a-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="a0f4a-129">Los marcos compilados JIT implementan tanto la interfaz `ICorDebugILFrame` como la interfaz ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0f4a-130">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a0f4a-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0f4a-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0f4a-131">Requirements</span></span>  
 <span data-ttu-id="a0f4a-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0f4a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0f4a-133">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0f4a-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0f4a-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0f4a-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0f4a-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0f4a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f4a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0f4a-136">See also</span></span>

- [<span data-ttu-id="a0f4a-137">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a0f4a-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
