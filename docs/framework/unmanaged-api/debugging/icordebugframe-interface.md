---
title: ICorDebugFrame Interfaz1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3d6c1a2bfd66e275b506d4465731c48cd7c6515
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416636"
---
# <a name="icordebugframe-interface1"></a><span data-ttu-id="16b27-102">ICorDebugFrame Interfaz1</span><span class="sxs-lookup"><span data-stu-id="16b27-102">ICorDebugFrame Interface1</span></span>
<span data-ttu-id="16b27-103">Representa un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="16b27-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16b27-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="16b27-104">Methods</span></span>  
  
|<span data-ttu-id="16b27-105">Método</span><span class="sxs-lookup"><span data-stu-id="16b27-105">Method</span></span>|<span data-ttu-id="16b27-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="16b27-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16b27-107">CreateStepper (método)</span><span class="sxs-lookup"><span data-stu-id="16b27-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="16b27-108">Obtiene un ICorDebugStepper para realizar operaciones de ejecución paso a paso en relación con este `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="16b27-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="16b27-109">GetCallee (método)</span><span class="sxs-lookup"><span data-stu-id="16b27-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="16b27-110">Obtiene un puntero a la `ICorDebugFrame` en la cadena actual que llama a este marco, o devuelve null si este es el marco más interno de la cadena.</span><span class="sxs-lookup"><span data-stu-id="16b27-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="16b27-111">GetCaller (método)</span><span class="sxs-lookup"><span data-stu-id="16b27-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="16b27-112">Obtiene un puntero a la `ICorDebugFrame` en la cadena actual que llama a este marco, o devuelve null si este es el marco más externo de la cadena.</span><span class="sxs-lookup"><span data-stu-id="16b27-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="16b27-113">GetChain (método)</span><span class="sxs-lookup"><span data-stu-id="16b27-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="16b27-114">Obtiene un puntero a la instancia de ICorDebugChain este `ICorDebugFrame` forma parte de.</span><span class="sxs-lookup"><span data-stu-id="16b27-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="16b27-115">GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="16b27-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="16b27-116">Obtiene un puntero a la ICorDebugCode asociada a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="16b27-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="16b27-117">GetFunction (método)</span><span class="sxs-lookup"><span data-stu-id="16b27-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="16b27-118">Obtiene un puntero a la instancia de ICorDebugFunction que contiene el código asociado con este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="16b27-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="16b27-119">GetFunctionToken (método)</span><span class="sxs-lookup"><span data-stu-id="16b27-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="16b27-120">Obtiene el token de metadatos para la función que contiene el código asociado con este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="16b27-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="16b27-121">GetStackRange (método)</span><span class="sxs-lookup"><span data-stu-id="16b27-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="16b27-122">Obtiene el intervalo de direcciones absolutas del marco de pila representado por este `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="16b27-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16b27-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16b27-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16b27-124">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="16b27-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16b27-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16b27-125">Requirements</span></span>  
 <span data-ttu-id="16b27-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16b27-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b27-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16b27-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16b27-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16b27-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16b27-129">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16b27-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b27-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="16b27-130">See Also</span></span>  
 [<span data-ttu-id="16b27-131">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="16b27-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
