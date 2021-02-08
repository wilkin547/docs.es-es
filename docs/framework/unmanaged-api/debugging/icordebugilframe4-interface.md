---
description: 'Más información acerca de: interfaz ICorDebugILFrame4'
title: ICorDebugILFrame4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: f2d29229f039509ed7799399f0d4d701e8cafba7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791210"
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="e454b-103">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e454b-103">ICorDebugILFrame4 Interface</span></span>

<span data-ttu-id="e454b-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="e454b-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e454b-105">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="e454b-105">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="e454b-106">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e454b-106">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e454b-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="e454b-107">Methods</span></span>  
  
|<span data-ttu-id="e454b-108">Método</span><span class="sxs-lookup"><span data-stu-id="e454b-108">Method</span></span>|<span data-ttu-id="e454b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e454b-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e454b-110">EnumerateLocalVariablesEx (método)</span><span class="sxs-lookup"><span data-stu-id="e454b-110">EnumerateLocalVariablesEx Method</span></span>](icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="e454b-111">Devuelve una lista de las variables locales disponibles en el marco actual.</span><span class="sxs-lookup"><span data-stu-id="e454b-111">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="e454b-112">GetCodeEx (método)</span><span class="sxs-lookup"><span data-stu-id="e454b-112">GetCodeEx Method</span></span>](icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="e454b-113">Devuelve el código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="e454b-113">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="e454b-114">GetLocalVariableEx (método)</span><span class="sxs-lookup"><span data-stu-id="e454b-114">GetLocalVariableEx Method</span></span>](icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="e454b-115">Devuelve el valor de una variable local en el marco de IL.</span><span class="sxs-lookup"><span data-stu-id="e454b-115">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e454b-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e454b-116">Remarks</span></span>  

 <span data-ttu-id="e454b-117">Estos métodos ofrecen funcionalidad además de la que proporcionan los métodos [enumeratelocalvariables (](icordebugilframe-enumeratelocalvariables-method.md), [getCode](icordebugframe-getcode-method.md)y [getlocalvariable (](icordebugilframe-getlocalvariable-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e454b-117">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md), [GetCode](icordebugframe-getcode-method.md), and [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="e454b-118">Cada método incluye un parámetro `flags` que especifica si otras variables locales o código definidos por una solicitud ReJIT del generador de perfiles son visibles.</span><span class="sxs-lookup"><span data-stu-id="e454b-118">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e454b-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e454b-119">Requirements</span></span>  

 <span data-ttu-id="e454b-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e454b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e454b-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e454b-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e454b-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e454b-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e454b-123">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e454b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e454b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e454b-124">See also</span></span>

- [<span data-ttu-id="e454b-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e454b-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e454b-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="e454b-126">Debugging</span></span>](index.md)
