---
title: Interfaz ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: ba138e79e0d6fb6f9c5e9c3efe3466f3c88cccae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782618"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="3f4dd-102">Interfaz ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="3f4dd-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="3f4dd-103">Representa un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3f4dd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3f4dd-104">Methods</span></span>  
  
|<span data-ttu-id="3f4dd-105">Método</span><span class="sxs-lookup"><span data-stu-id="3f4dd-105">Method</span></span>|<span data-ttu-id="3f4dd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f4dd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f4dd-107">CreateStepper (método)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-107">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="3f4dd-108">Obtiene un ICorDebugStepper para realizar operaciones de ejecución paso a paso con respecto a este `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="3f4dd-109">GetCallee (método)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-109">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="3f4dd-110">Obtiene un puntero al `ICorDebugFrame` en la cadena actual a la que este marco llamó, o devuelve NULL si se trata del marco más interno de la cadena.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="3f4dd-111">GetCaller (método)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-111">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="3f4dd-112">Obtiene un puntero al `ICorDebugFrame` en la cadena actual que llamó a este marco, o devuelve NULL si se trata del marco más externo de la cadena.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="3f4dd-113">GetChain (método)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-113">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="3f4dd-114">Obtiene un puntero al elemento ICorDebugChain del que forma parte este `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="3f4dd-115">GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-115">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="3f4dd-116">Obtiene un puntero a la clase ICorDebugCode asociada a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="3f4dd-117">GetFunction (método)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-117">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="3f4dd-118">Obtiene un puntero a la clase ICorDebugFunction que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="3f4dd-119">GetFunctionToken (método)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-119">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="3f4dd-120">Obtiene el símbolo (token) de metadatos para la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="3f4dd-121">GetStackRange (método)</span><span class="sxs-lookup"><span data-stu-id="3f4dd-121">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="3f4dd-122">Obtiene el intervalo de direcciones absolutas del marco de pila representado por este `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f4dd-123">Notas</span><span class="sxs-lookup"><span data-stu-id="3f4dd-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f4dd-124">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3f4dd-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f4dd-125">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3f4dd-125">Requirements</span></span>  
 <span data-ttu-id="3f4dd-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f4dd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f4dd-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f4dd-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f4dd-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f4dd-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f4dd-129">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f4dd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4dd-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f4dd-130">See also</span></span>

- [<span data-ttu-id="3f4dd-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3f4dd-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
