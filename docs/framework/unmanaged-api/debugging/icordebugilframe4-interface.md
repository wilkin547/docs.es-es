---
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
ms.openlocfilehash: 7d0f3661c7941c5f2f85fa5b0b67af213de75f05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724954"
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="51e5e-102">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51e5e-102">ICorDebugILFrame4 Interface</span></span>

<span data-ttu-id="51e5e-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="51e5e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="51e5e-104">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="51e5e-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="51e5e-105">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="51e5e-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51e5e-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="51e5e-106">Methods</span></span>  
  
|<span data-ttu-id="51e5e-107">Método</span><span class="sxs-lookup"><span data-stu-id="51e5e-107">Method</span></span>|<span data-ttu-id="51e5e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="51e5e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51e5e-109">EnumerateLocalVariablesEx (método)</span><span class="sxs-lookup"><span data-stu-id="51e5e-109">EnumerateLocalVariablesEx Method</span></span>](icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="51e5e-110">Devuelve una lista de las variables locales disponibles en el marco actual.</span><span class="sxs-lookup"><span data-stu-id="51e5e-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="51e5e-111">GetCodeEx (método)</span><span class="sxs-lookup"><span data-stu-id="51e5e-111">GetCodeEx Method</span></span>](icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="51e5e-112">Devuelve el código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="51e5e-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="51e5e-113">GetLocalVariableEx (método)</span><span class="sxs-lookup"><span data-stu-id="51e5e-113">GetLocalVariableEx Method</span></span>](icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="51e5e-114">Devuelve el valor de una variable local en el marco de IL.</span><span class="sxs-lookup"><span data-stu-id="51e5e-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51e5e-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51e5e-115">Remarks</span></span>  

 <span data-ttu-id="51e5e-116">Estos métodos ofrecen funcionalidad además de la que proporcionan los métodos [enumeratelocalvariables (](icordebugilframe-enumeratelocalvariables-method.md), [getCode](icordebugframe-getcode-method.md)y [getlocalvariable (](icordebugilframe-getlocalvariable-method.md) .</span><span class="sxs-lookup"><span data-stu-id="51e5e-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md), [GetCode](icordebugframe-getcode-method.md), and [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="51e5e-117">Cada método incluye un parámetro `flags` que especifica si otras variables locales o código definidos por una solicitud ReJIT del generador de perfiles son visibles.</span><span class="sxs-lookup"><span data-stu-id="51e5e-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51e5e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51e5e-118">Requirements</span></span>  

 <span data-ttu-id="51e5e-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51e5e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51e5e-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51e5e-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51e5e-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51e5e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51e5e-122">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51e5e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e5e-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51e5e-123">See also</span></span>

- [<span data-ttu-id="51e5e-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="51e5e-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="51e5e-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="51e5e-125">Debugging</span></span>](index.md)
