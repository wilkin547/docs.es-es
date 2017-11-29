---
title: ICorDebugILFrame4 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame4
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80b42a2ed4e93fd5e4c662bab34b111fe0757890
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="d8eda-102">ICorDebugILFrame4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8eda-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="d8eda-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="d8eda-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d8eda-104">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="d8eda-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="d8eda-105">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="d8eda-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8eda-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="d8eda-106">Methods</span></span>  
  
|<span data-ttu-id="d8eda-107">Método</span><span class="sxs-lookup"><span data-stu-id="d8eda-107">Method</span></span>|<span data-ttu-id="d8eda-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8eda-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8eda-109">EnumerateLocalVariablesEx (método)</span><span class="sxs-lookup"><span data-stu-id="d8eda-109">EnumerateLocalVariablesEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="d8eda-110">Devuelve una lista de las variables locales disponibles en el marco actual.</span><span class="sxs-lookup"><span data-stu-id="d8eda-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="d8eda-111">GetCodeEx (método)</span><span class="sxs-lookup"><span data-stu-id="d8eda-111">GetCodeEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="d8eda-112">Devuelve el código que este marco de pila está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="d8eda-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="d8eda-113">GetLocalVariableEx (método)</span><span class="sxs-lookup"><span data-stu-id="d8eda-113">GetLocalVariableEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="d8eda-114">Devuelve el valor de una variable local en el marco de IL.</span><span class="sxs-lookup"><span data-stu-id="d8eda-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8eda-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8eda-115">Remarks</span></span>  
 <span data-ttu-id="d8eda-116">Estos métodos ofrecen funcionalidad a la que proporcionan la [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), y [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="d8eda-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), and [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="d8eda-117">Cada método incluye un parámetro `flags` que especifica si otras variables locales o código definidos por una solicitud ReJIT del generador de perfiles son visibles.</span><span class="sxs-lookup"><span data-stu-id="d8eda-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8eda-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8eda-118">Requirements</span></span>  
 <span data-ttu-id="d8eda-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8eda-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8eda-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8eda-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8eda-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8eda-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8eda-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8eda-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8eda-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8eda-123">See Also</span></span>  
 [<span data-ttu-id="d8eda-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d8eda-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d8eda-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="d8eda-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
