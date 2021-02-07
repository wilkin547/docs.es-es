---
description: 'Más información sobre: ICorDebugFrame (interfaz)'
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
ms.openlocfilehash: d0fd629672d535f89fe78c178032937443d9dfbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692854"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="4509d-103">Interfaz ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="4509d-103">ICorDebugFrame Interface</span></span>

<span data-ttu-id="4509d-104">Representa un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="4509d-104">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4509d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4509d-105">Methods</span></span>  
  
|<span data-ttu-id="4509d-106">Método</span><span class="sxs-lookup"><span data-stu-id="4509d-106">Method</span></span>|<span data-ttu-id="4509d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4509d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4509d-108">CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="4509d-108">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="4509d-109">Obtiene un ICorDebugStepper para realizar operaciones de ejecución paso a paso con respecto a este `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="4509d-109">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="4509d-110">Método GetCallee</span><span class="sxs-lookup"><span data-stu-id="4509d-110">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="4509d-111">Obtiene un puntero al `ICorDebugFrame` en la cadena actual a la que este marco llamó, o devuelve NULL si se trata del marco más interno de la cadena.</span><span class="sxs-lookup"><span data-stu-id="4509d-111">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="4509d-112">Método GetCaller</span><span class="sxs-lookup"><span data-stu-id="4509d-112">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="4509d-113">Obtiene un puntero al `ICorDebugFrame` en la cadena actual que llamó a este marco, o devuelve NULL si se trata del marco más externo de la cadena.</span><span class="sxs-lookup"><span data-stu-id="4509d-113">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="4509d-114">Método GetChain</span><span class="sxs-lookup"><span data-stu-id="4509d-114">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="4509d-115">Obtiene un puntero al `ICorDebugFrame` elemento ICorDebugChain del que forma parte.</span><span class="sxs-lookup"><span data-stu-id="4509d-115">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="4509d-116">Método GetCode</span><span class="sxs-lookup"><span data-stu-id="4509d-116">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="4509d-117">Obtiene un puntero a la clase ICorDebugCode asociada a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="4509d-117">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4509d-118">Método GetFunction</span><span class="sxs-lookup"><span data-stu-id="4509d-118">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="4509d-119">Obtiene un puntero a la clase ICorDebugFunction que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="4509d-119">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4509d-120">Método GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="4509d-120">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="4509d-121">Obtiene el símbolo (token) de metadatos para la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="4509d-121">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="4509d-122">GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="4509d-122">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="4509d-123">Obtiene el intervalo de direcciones absolutas del marco de pila representado por este `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="4509d-123">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4509d-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4509d-124">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4509d-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4509d-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4509d-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4509d-126">Requirements</span></span>  

 <span data-ttu-id="4509d-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4509d-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4509d-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4509d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4509d-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4509d-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4509d-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4509d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4509d-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4509d-131">See also</span></span>

- [<span data-ttu-id="4509d-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4509d-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
