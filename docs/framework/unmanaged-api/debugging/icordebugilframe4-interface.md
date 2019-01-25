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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb3f55a8a0ddff6c3202d15dc4704d443cabb44d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656952"
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="94199-102">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94199-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="94199-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="94199-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="94199-104">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="94199-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="94199-105">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="94199-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94199-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="94199-106">Methods</span></span>  
  
|<span data-ttu-id="94199-107">Método</span><span class="sxs-lookup"><span data-stu-id="94199-107">Method</span></span>|<span data-ttu-id="94199-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="94199-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94199-109">EnumerateLocalVariablesEx (método)</span><span class="sxs-lookup"><span data-stu-id="94199-109">EnumerateLocalVariablesEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="94199-110">Devuelve una lista de las variables locales disponibles en el marco actual.</span><span class="sxs-lookup"><span data-stu-id="94199-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="94199-111">GetCodeEx (método)</span><span class="sxs-lookup"><span data-stu-id="94199-111">GetCodeEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="94199-112">Devuelve el código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="94199-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="94199-113">GetLocalVariableEx (método)</span><span class="sxs-lookup"><span data-stu-id="94199-113">GetLocalVariableEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="94199-114">Devuelve el valor de una variable local en el marco de IL.</span><span class="sxs-lookup"><span data-stu-id="94199-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94199-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94199-115">Remarks</span></span>  
 <span data-ttu-id="94199-116">Estos métodos ofrecen la funcionalidad que proporciona a la que el [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), y [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="94199-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), and [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="94199-117">Cada método incluye un parámetro `flags` que especifica si otras variables locales o código definidos por una solicitud ReJIT del generador de perfiles son visibles.</span><span class="sxs-lookup"><span data-stu-id="94199-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94199-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94199-118">Requirements</span></span>  
 <span data-ttu-id="94199-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94199-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94199-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94199-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94199-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94199-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94199-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94199-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94199-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="94199-123">See also</span></span>
- [<span data-ttu-id="94199-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="94199-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="94199-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="94199-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
