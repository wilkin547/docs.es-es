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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135244"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="1db84-102">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1db84-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="1db84-103">Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="1db84-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1db84-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1db84-104">Methods</span></span>  
  
|<span data-ttu-id="1db84-105">Método</span><span class="sxs-lookup"><span data-stu-id="1db84-105">Method</span></span>|<span data-ttu-id="1db84-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1db84-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1db84-107">Método GetRegisters</span><span class="sxs-lookup"><span data-stu-id="1db84-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="1db84-108">Obtiene el valor de cada registro (en el equipo que está ejecutando el código) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="1db84-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="1db84-109">Método GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="1db84-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="1db84-110">Obtiene un poco de máscara que indica que se registra en este `ICorDebugRegisterSet` están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="1db84-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="1db84-111">Método GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="1db84-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="1db84-112">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1db84-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="1db84-113">Método SetRegisters</span><span class="sxs-lookup"><span data-stu-id="1db84-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="1db84-114">No se ha implementado para la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1db84-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="1db84-115">Método SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="1db84-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="1db84-116">No se ha implementado para .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="1db84-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1db84-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1db84-117">Remarks</span></span>  
 <span data-ttu-id="1db84-118">El `ICorDebugRegisterSet` interfaz admite registros sólo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="1db84-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="1db84-119">Use la [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interfaz en plataformas como IA-64 que requieran registros adicionales.</span><span class="sxs-lookup"><span data-stu-id="1db84-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1db84-120">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1db84-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1db84-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1db84-121">Requirements</span></span>  
 <span data-ttu-id="1db84-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1db84-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1db84-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1db84-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1db84-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1db84-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1db84-125">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1db84-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1db84-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1db84-126">See also</span></span>

- [<span data-ttu-id="1db84-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1db84-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1db84-128">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1db84-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
