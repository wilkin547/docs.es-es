---
description: 'Más información sobre: ICorDebugRegisterSet (interfaz)'
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
ms.openlocfilehash: 7d888e9e395e9f5fa88c6a6d96b2b8e3171ef4ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690787"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="15ce5-103">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15ce5-103">ICorDebugRegisterSet Interface</span></span>

<span data-ttu-id="15ce5-104">Representa el conjunto de registros disponibles en el equipo que está ejecutando código actualmente.</span><span class="sxs-lookup"><span data-stu-id="15ce5-104">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15ce5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="15ce5-105">Methods</span></span>  
  
|<span data-ttu-id="15ce5-106">Método</span><span class="sxs-lookup"><span data-stu-id="15ce5-106">Method</span></span>|<span data-ttu-id="15ce5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="15ce5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15ce5-108">GetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="15ce5-108">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="15ce5-109">Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="15ce5-109">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="15ce5-110">GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="15ce5-110">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="15ce5-111">Obtiene una máscara de bits que indica qué registros de `ICorDebugRegisterSet` están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="15ce5-111">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="15ce5-112">GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="15ce5-112">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="15ce5-113">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="15ce5-113">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="15ce5-114">Método SetRegisters</span><span class="sxs-lookup"><span data-stu-id="15ce5-114">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="15ce5-115">No se ha implementado para la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="15ce5-115">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="15ce5-116">Método SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="15ce5-116">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="15ce5-117">No se ha implementado para el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="15ce5-117">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15ce5-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15ce5-118">Remarks</span></span>  

 <span data-ttu-id="15ce5-119">La `ICorDebugRegisterSet` interfaz solo admite registros de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="15ce5-119">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="15ce5-120">Use la interfaz [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) en plataformas como IA-64 que requieran registros adicionales.</span><span class="sxs-lookup"><span data-stu-id="15ce5-120">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15ce5-121">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="15ce5-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ce5-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15ce5-122">Requirements</span></span>  

 <span data-ttu-id="15ce5-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15ce5-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ce5-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15ce5-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15ce5-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15ce5-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15ce5-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ce5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ce5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="15ce5-127">See also</span></span>

- [<span data-ttu-id="15ce5-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="15ce5-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="15ce5-129">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15ce5-129">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
