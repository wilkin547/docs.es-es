---
description: 'Más información sobre: ICorDebugILFrame (interfaz)'
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
ms.openlocfilehash: 251fa18151ff286bee3e1bcf7707bf5f7145b4f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791366"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="3d901-103">Interfaz ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="3d901-103">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="3d901-104">Representa un marco de pila del código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="3d901-104">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="3d901-105">Esta interfaz es una subclase de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="3d901-105">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d901-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="3d901-106">Methods</span></span>  
  
|<span data-ttu-id="3d901-107">Método</span><span class="sxs-lookup"><span data-stu-id="3d901-107">Method</span></span>|<span data-ttu-id="3d901-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d901-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d901-109">Método CanSetIP</span><span class="sxs-lookup"><span data-stu-id="3d901-109">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="3d901-110">Obtiene un valor que indica si es seguro establecer el puntero de instrucción en la ubicación de desplazamiento especificada.</span><span class="sxs-lookup"><span data-stu-id="3d901-110">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="3d901-111">Método EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="3d901-111">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="3d901-112">Obtiene un enumerador para los argumentos de este marco.</span><span class="sxs-lookup"><span data-stu-id="3d901-112">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="3d901-113">Método EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="3d901-113">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="3d901-114">Obtiene un enumerador para las variables locales de este marco.</span><span class="sxs-lookup"><span data-stu-id="3d901-114">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="3d901-115">Método GetArgument</span><span class="sxs-lookup"><span data-stu-id="3d901-115">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="3d901-116">Obtiene el valor del argumento especificado en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="3d901-116">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="3d901-117">Método GetIP</span><span class="sxs-lookup"><span data-stu-id="3d901-117">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="3d901-118">Obtiene el valor del puntero de instrucción y un valor de combinación bit a bit que describe cómo se obtuvo el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="3d901-118">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="3d901-119">Método GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="3d901-119">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="3d901-120">Obtiene el valor de la variable local especificada en este marco de pila de MSIL.</span><span class="sxs-lookup"><span data-stu-id="3d901-120">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="3d901-121">Método GetStackDepth</span><span class="sxs-lookup"><span data-stu-id="3d901-121">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="3d901-122">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="3d901-122">Not implemented.</span></span>|  
|[<span data-ttu-id="3d901-123">Método GetStackValue</span><span class="sxs-lookup"><span data-stu-id="3d901-123">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="3d901-124">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="3d901-124">Not implemented.</span></span>|  
|[<span data-ttu-id="3d901-125">SetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="3d901-125">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="3d901-126">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código MSIL.</span><span class="sxs-lookup"><span data-stu-id="3d901-126">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d901-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3d901-127">Remarks</span></span>  

 <span data-ttu-id="3d901-128">La `ICorDebugILFrame` interfaz es una interfaz de ICorDebugFrame especializada.</span><span class="sxs-lookup"><span data-stu-id="3d901-128">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="3d901-129">Se usa para los marcos de código MSIL o para los marcos compilados Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="3d901-129">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="3d901-130">Los marcos compilados con JIT implementan la interfaz `ICorDebugILFrame` y la interfaz ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="3d901-130">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d901-131">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3d901-131">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d901-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d901-132">Requirements</span></span>  

 <span data-ttu-id="3d901-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d901-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d901-134">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d901-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d901-135">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d901-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d901-136">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d901-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d901-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d901-137">See also</span></span>

- [<span data-ttu-id="3d901-138">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3d901-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
