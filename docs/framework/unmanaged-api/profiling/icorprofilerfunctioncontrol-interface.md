---
title: ICorProfilerFunctionControl (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 721ee27522b316a561e2f64a322c225cb85a44c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211444"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="e76e8-102">ICorProfilerFunctionControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e76e8-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="e76e8-103">Proporciona métodos que permiten a un generador de perfiles de código comunicarse con Common Language Runtime (CLR) para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.</span><span class="sxs-lookup"><span data-stu-id="e76e8-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e76e8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e76e8-104">Methods</span></span>  
  
|<span data-ttu-id="e76e8-105">Método</span><span class="sxs-lookup"><span data-stu-id="e76e8-105">Method</span></span>|<span data-ttu-id="e76e8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e76e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e76e8-107">SetCodegenFlags (método)</span><span class="sxs-lookup"><span data-stu-id="e76e8-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="e76e8-108">Establece una o más marcas de la [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeración a la generación de código de control para un just-in-time (JIT) vuelve a compilar la función.</span><span class="sxs-lookup"><span data-stu-id="e76e8-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="e76e8-109">SetILFunctionBody (método)</span><span class="sxs-lookup"><span data-stu-id="e76e8-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="e76e8-110">Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.</span><span class="sxs-lookup"><span data-stu-id="e76e8-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="e76e8-111">SetILInstrumentedCodeMap (método)</span><span class="sxs-lookup"><span data-stu-id="e76e8-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="e76e8-112">Establece un mapa de código para la función especificada usando las entradas del mapa de Common Intermediate Language (CIL) especificadas.</span><span class="sxs-lookup"><span data-stu-id="e76e8-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e76e8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e76e8-113">Remarks</span></span>  
 <span data-ttu-id="e76e8-114">La interfaz `ICorProfilerFunctionControl` proporciona métodos para controlar la generación de código para una única función que se ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="e76e8-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="e76e8-115">El generador de perfiles Obtiene una instancia de esta interfaz a través de la [Icorprofilercallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e76e8-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="e76e8-116">Cada instancia de `ICorProfilerFunctionControl` controla todas las instancias de una función.</span><span class="sxs-lookup"><span data-stu-id="e76e8-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e76e8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e76e8-117">Requirements</span></span>  
 <span data-ttu-id="e76e8-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e76e8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e76e8-119">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e76e8-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e76e8-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e76e8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e76e8-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e76e8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e76e8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e76e8-122">See also</span></span>

- [<span data-ttu-id="e76e8-123">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e76e8-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="e76e8-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e76e8-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="e76e8-125">EnumJITedFunctions2 (método)</span><span class="sxs-lookup"><span data-stu-id="e76e8-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
