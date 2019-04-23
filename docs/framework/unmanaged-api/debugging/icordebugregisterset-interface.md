---
title: ICorDebugRegisterSet (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b0a5d80d984a3c696b178c4d8c936bd47354945
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135244"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="46def-102">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46def-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="46def-103">Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="46def-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="46def-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="46def-104">Methods</span></span>  
  
|<span data-ttu-id="46def-105">Método</span><span class="sxs-lookup"><span data-stu-id="46def-105">Method</span></span>|<span data-ttu-id="46def-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="46def-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="46def-107">GetRegisters (método)</span><span class="sxs-lookup"><span data-stu-id="46def-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="46def-108">Obtiene el valor de cada registro (en el equipo que está ejecutando el código) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="46def-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="46def-109">GetRegistersAvailable (método)</span><span class="sxs-lookup"><span data-stu-id="46def-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="46def-110">Obtiene un poco de máscara que indica que se registra en este `ICorDebugRegisterSet` están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="46def-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="46def-111">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="46def-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="46def-112">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="46def-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="46def-113">SetRegisters (método)</span><span class="sxs-lookup"><span data-stu-id="46def-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="46def-114">No se ha implementado para la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46def-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="46def-115">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="46def-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="46def-116">No se ha implementado para .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="46def-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46def-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46def-117">Remarks</span></span>  
 <span data-ttu-id="46def-118">El `ICorDebugRegisterSet` interfaz admite registros sólo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="46def-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="46def-119">Use la [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interfaz en plataformas como IA-64 que requieran registros adicionales.</span><span class="sxs-lookup"><span data-stu-id="46def-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46def-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="46def-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46def-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46def-121">Requirements</span></span>  
 <span data-ttu-id="46def-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46def-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46def-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46def-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46def-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46def-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46def-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46def-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46def-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="46def-126">See also</span></span>

- [<span data-ttu-id="46def-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="46def-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="46def-128">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46def-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
