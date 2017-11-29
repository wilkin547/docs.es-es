---
title: ICorProfilerFunctionControl (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl
helpviewer_keywords: ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09a0a839c9cd69c7926c19cceffc56ee928f2f02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="b472d-102">ICorProfilerFunctionControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b472d-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="b472d-103">Proporciona métodos que permiten a un generador de perfiles de código comunicarse con Common Language Runtime (CLR) para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.</span><span class="sxs-lookup"><span data-stu-id="b472d-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b472d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b472d-104">Methods</span></span>  
  
|<span data-ttu-id="b472d-105">Método</span><span class="sxs-lookup"><span data-stu-id="b472d-105">Method</span></span>|<span data-ttu-id="b472d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b472d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b472d-107">SetCodegenFlags (método)</span><span class="sxs-lookup"><span data-stu-id="b472d-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="b472d-108">Establece una o más marcas de la [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeración para controlar la generación de código de un just-in-time (JIT) vuelva a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="b472d-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="b472d-109">SetILFunctionBody (método)</span><span class="sxs-lookup"><span data-stu-id="b472d-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="b472d-110">Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.</span><span class="sxs-lookup"><span data-stu-id="b472d-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="b472d-111">SetILInstrumentedCodeMap (método)</span><span class="sxs-lookup"><span data-stu-id="b472d-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="b472d-112">Establece un mapa de código para la función especificada usando las entradas del mapa de Common Intermediate Language (CIL) especificadas.</span><span class="sxs-lookup"><span data-stu-id="b472d-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b472d-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b472d-113">Remarks</span></span>  
 <span data-ttu-id="b472d-114">La interfaz `ICorProfilerFunctionControl` proporciona métodos para controlar la generación de código para una única función que se ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="b472d-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="b472d-115">El generador de perfiles Obtiene una instancia de esta interfaz mediante la [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b472d-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="b472d-116">Cada instancia de `ICorProfilerFunctionControl` controla todas las instancias de una función.</span><span class="sxs-lookup"><span data-stu-id="b472d-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b472d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b472d-117">Requirements</span></span>  
 <span data-ttu-id="b472d-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b472d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b472d-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b472d-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b472d-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b472d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b472d-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b472d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b472d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b472d-122">See Also</span></span>  
 [<span data-ttu-id="b472d-123">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b472d-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="b472d-124">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b472d-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="b472d-125">EnumJITedFunctions2 (método)</span><span class="sxs-lookup"><span data-stu-id="b472d-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
