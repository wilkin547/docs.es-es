---
title: ICorDebugRegisterSet (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet
helpviewer_keywords: ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ccff205758dee2ffc6a6432ab20b3310147eb06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="fbd7a-102">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbd7a-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="fbd7a-103">Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fbd7a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fbd7a-104">Methods</span></span>  
  
|<span data-ttu-id="fbd7a-105">Método</span><span class="sxs-lookup"><span data-stu-id="fbd7a-105">Method</span></span>|<span data-ttu-id="fbd7a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbd7a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fbd7a-107">GetRegisters (método)</span><span class="sxs-lookup"><span data-stu-id="fbd7a-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="fbd7a-108">Obtiene el valor de cada registro (en el equipo que está ejecutando el código) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="fbd7a-109">GetRegistersAvailable (método)</span><span class="sxs-lookup"><span data-stu-id="fbd7a-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="fbd7a-110">Obtiene un poco de máscara que indica que se registra en esta `ICorDebugRegisterSet` están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="fbd7a-111">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="fbd7a-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="fbd7a-112">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="fbd7a-113">SetRegisters (método)</span><span class="sxs-lookup"><span data-stu-id="fbd7a-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="fbd7a-114">No se implementa para la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="fbd7a-115">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="fbd7a-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="fbd7a-116">No se implementa para .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbd7a-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fbd7a-117">Remarks</span></span>  
 <span data-ttu-id="fbd7a-118">La `ICorDebugRegisterSet` interfaz es compatible con registros sólo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="fbd7a-119">Use la [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interfaz en plataformas como IA-64 que requieran registros adicionales.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbd7a-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="fbd7a-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbd7a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbd7a-121">Requirements</span></span>  
 <span data-ttu-id="fbd7a-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbd7a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbd7a-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbd7a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbd7a-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbd7a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbd7a-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbd7a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd7a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbd7a-126">See Also</span></span>  
 [<span data-ttu-id="fbd7a-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fbd7a-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="fbd7a-128">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbd7a-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
