---
title: "ICorProfilerCallback6::GetAssemblyReferences (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc2e80d6d8207a869d43beb46cc9448bdd86dfec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="3d211-102">ICorProfilerCallback6::GetAssemblyReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="3d211-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="3d211-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="3d211-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3d211-104">Notifica al generador de perfiles que un ensamblado está en una etapa de carga muy temprana, cuando Common Language Runtime realiza un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d211-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d211-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d211-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d211-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d211-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="3d211-107">[in] Ruta de acceso y nombre del ensamblado cuyos metadatos se modificarán.</span><span class="sxs-lookup"><span data-stu-id="3d211-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="3d211-108">[in] Un puntero a la dirección de un [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interfaz que especifica el ensamblado hace referencia a agregar.</span><span class="sxs-lookup"><span data-stu-id="3d211-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d211-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3d211-109">Return Value</span></span>  
 <span data-ttu-id="3d211-110">Los valores devueltos de esta devolución de llamada se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="3d211-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d211-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d211-111">Remarks</span></span>  
 <span data-ttu-id="3d211-112">Esta devolución de llamada se controla estableciendo la [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) marca de máscara de eventos cuando se llama a la [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="3d211-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="3d211-113">Si el generador de perfiles se registra para el [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) método de devolución de llamada, el tiempo de ejecución pasa la ruta de acceso y el nombre del ensamblado que se va a cargar, junto con un puntero a un [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objeto de interfaz a ese método.</span><span class="sxs-lookup"><span data-stu-id="3d211-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="3d211-114">El generador de perfiles, a continuación, puede llamar a la [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) método con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` objeto para cada ensamblado de destino lo planeado hacer referencia desde el ensamblado especificado en el `GetAssemblyReferences` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3d211-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="3d211-115">Use la devolución de llamada `GetAssemblyReferences` solo si el generador de perfiles tiene que modificar los metadatos de un ensamblado para agregar referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d211-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="3d211-116">(Pero tenga en cuenta que la modificación real de los metadatos de un ensamblado se realiza en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)método de devolución de llamada.) El generador de perfiles deben implementar el método de devolución de llamada `GetAssemblyReferences` para informar a Common Language Runtime (CLR) que se agregarán referencias de ensamblado cuando el módulo se haya cargado.</span><span class="sxs-lookup"><span data-stu-id="3d211-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="3d211-117">Esto garantiza que las decisiones que tome CLR acerca del uso compartido de ensamblados en esta fase temprana seguirán siendo válidas aunque el generador de perfiles tenga planeado modificar las referencias de ensamblado de metadatos más adelante.</span><span class="sxs-lookup"><span data-stu-id="3d211-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="3d211-118">De esta manera se pueden evitar algunas instancias en las que las modificaciones de los metadatos del generador de perfiles provocan un error `SECURITY_E_INCOMPATIBLE_SHARE`.</span><span class="sxs-lookup"><span data-stu-id="3d211-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="3d211-119">El generador de perfiles usa la [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objeto proporcionado por este método para agregar referencias de ensamblado para el Rastreador de cierres de referencia de ensamblado CLR.</span><span class="sxs-lookup"><span data-stu-id="3d211-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="3d211-120">El [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objeto debe utilizarse únicamente desde dentro de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3d211-120">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="3d211-121">Llamadas a la [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) método desde esta devolución de llamada no producen metadatos modificados, pero solo en un rastreo de cierre de referencias de ensamblado modificado.</span><span class="sxs-lookup"><span data-stu-id="3d211-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="3d211-122">El generador de perfiles aún tendrá que usar un [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) objeto que se va a agregar explícitamente las referencias de ensamblado desde el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada para la referencia ensamblado, incluso si implementa el `GetAssemblyReferences` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3d211-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="3d211-123">El generador de perfiles debe estar preparado para recibir llamadas duplicadas a esta devolución de llamada para el mismo ensamblado y debe responder de forma idéntica para cada de estas llamadas duplicadas (realizando el mismo conjunto de [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) llamadas).</span><span class="sxs-lookup"><span data-stu-id="3d211-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d211-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d211-124">Requirements</span></span>  
 <span data-ttu-id="3d211-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d211-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d211-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d211-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d211-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d211-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d211-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d211-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d211-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d211-129">See Also</span></span>  
 [<span data-ttu-id="3d211-130">ICorProfilerCallback6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d211-130">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 [<span data-ttu-id="3d211-131">ModuleLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="3d211-131">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="3d211-132">COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="3d211-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 [<span data-ttu-id="3d211-133">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d211-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
