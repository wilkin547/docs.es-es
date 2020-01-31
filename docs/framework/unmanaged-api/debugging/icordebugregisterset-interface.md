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
ms.openlocfilehash: f435db28d5c85d576f69e7612841fc46ae142332
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792080"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="fc386-102">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc386-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="fc386-103">Representa el conjunto de registros disponibles en el equipo que está ejecutando código actualmente.</span><span class="sxs-lookup"><span data-stu-id="fc386-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc386-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fc386-104">Methods</span></span>  
  
|<span data-ttu-id="fc386-105">Método</span><span class="sxs-lookup"><span data-stu-id="fc386-105">Method</span></span>|<span data-ttu-id="fc386-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc386-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc386-107">GetRegisters (método)</span><span class="sxs-lookup"><span data-stu-id="fc386-107">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="fc386-108">Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="fc386-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="fc386-109">GetRegistersAvailable (método)</span><span class="sxs-lookup"><span data-stu-id="fc386-109">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="fc386-110">Obtiene una máscara de bits que indica qué registros de este `ICorDebugRegisterSet` están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="fc386-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="fc386-111">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="fc386-111">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="fc386-112">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="fc386-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="fc386-113">SetRegisters (método)</span><span class="sxs-lookup"><span data-stu-id="fc386-113">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="fc386-114">No se ha implementado para la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="fc386-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="fc386-115">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="fc386-115">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="fc386-116">No se ha implementado para el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="fc386-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc386-117">Notas</span><span class="sxs-lookup"><span data-stu-id="fc386-117">Remarks</span></span>  
 <span data-ttu-id="fc386-118">La interfaz de `ICorDebugRegisterSet` solo admite registros de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="fc386-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="fc386-119">Use la interfaz [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) en plataformas como IA-64 que requieran registros adicionales.</span><span class="sxs-lookup"><span data-stu-id="fc386-119">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc386-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="fc386-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc386-121">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="fc386-121">Requirements</span></span>  
 <span data-ttu-id="fc386-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc386-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc386-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc386-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc386-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc386-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc386-125">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc386-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc386-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc386-126">See also</span></span>

- [<span data-ttu-id="fc386-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fc386-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc386-128">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc386-128">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
