---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted Método
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177051"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a><span data-ttu-id="3a683-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Método</span><span class="sxs-lookup"><span data-stu-id="3a683-102">ICorProfilerCallback8::DynamicMethodJITCompilationStarted Method</span></span>
<span data-ttu-id="3a683-103">[Soportado en .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="3a683-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  
  
<span data-ttu-id="3a683-104">Notifica al generador de perfiles cada vez que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="3a683-104">Notifies the profiler whenever JIT compilation of a dynamic method has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a683-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a683-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a683-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a683-106">Parameters</span></span>  
<span data-ttu-id="3a683-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="3a683-107">[in] `functionId`</span></span>  
<span data-ttu-id="3a683-108">Identificador de la función en memoria para la que se inicia la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="3a683-108">The identifier of the in-memory function for which JIT compilation is started.</span></span>

<span data-ttu-id="3a683-109">[en] `fIsSafeToBlock` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada vuelva de esta devolución de 
 `true` llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3a683-109">[in] `fIsSafeToBlock`
`true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  

<span data-ttu-id="3a683-110">[en] `pILHeader` Puntero al primer byte del encabezado IL del método.</span><span class="sxs-lookup"><span data-stu-id="3a683-110">[in] `pILHeader` A pointer to the first byte of the method's IL header.</span></span>

<span data-ttu-id="3a683-111">[en] `cbILHeader` El número de bytes en el encabezado de IL.</span><span class="sxs-lookup"><span data-stu-id="3a683-111">[in] `cbILHeader` The number of bytes in the IL header.</span></span>

## <a name="remarks"></a><span data-ttu-id="3a683-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3a683-112">Remarks</span></span>  

<span data-ttu-id="3a683-113">Esta devolución de llamada se desencadena siempre que se compila un método dinámico JIT.</span><span class="sxs-lookup"><span data-stu-id="3a683-113">This callback is triggered whenever a dynamic method is JIT-compiled.</span></span> <span data-ttu-id="3a683-114">Esto incluye varios talones de IL y métodos LCG.</span><span class="sxs-lookup"><span data-stu-id="3a683-114">This includes various IL stubs and LCG methods.</span></span> <span data-ttu-id="3a683-115">Su objetivo es proporcionar a los escritores de generadores de perfiles suficiente información para identificar el método compilado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3a683-115">Its goal is to provide profiler writers with enough information to identify the compiled method to users.</span></span>

> [!NOTE]
> <span data-ttu-id="3a683-116">`functionId`los valores no se pueden usar para resolver en sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="3a683-116">`functionId` values cannot be used to resolve to their metadata tokens, because dynamic methods have no metadata.</span></span>

<span data-ttu-id="3a683-117">El `pILHeader` puntero solo es válido durante la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3a683-117">The `pILHeader` pointer is only valid during the callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a683-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a683-118">Requirements</span></span>  
 <span data-ttu-id="3a683-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a683-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a683-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a683-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a683-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a683-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a683-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3a683-122">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a683-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a683-123">See also</span></span>

- [<span data-ttu-id="3a683-124">DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="3a683-124">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="3a683-125">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a683-125">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)
