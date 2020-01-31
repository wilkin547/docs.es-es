---
title: ICorProfilerCallback6::GetAssemblyReferences (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 0717ef5fdb6c0447ceeb801f239be08f8cca5988
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865056"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="f6b4d-102">ICorProfilerCallback6::GetAssemblyReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="f6b4d-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="f6b4d-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f6b4d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f6b4d-104">Notifica al generador de perfiles que un ensamblado está en una etapa de carga muy temprana, cuando Common Language Runtime realiza un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b4d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6b4d-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6b4d-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="f6b4d-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="f6b4d-107">[in] Ruta de acceso y nombre del ensamblado cuyos metadatos se modificarán.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="f6b4d-108">de Puntero a la dirección de una interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) que especifica las referencias de ensamblado que se van a agregar.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6b4d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f6b4d-109">Return Value</span></span>  
 <span data-ttu-id="f6b4d-110">Los valores devueltos de esta devolución de llamada se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6b4d-111">Notas</span><span class="sxs-lookup"><span data-stu-id="f6b4d-111">Remarks</span></span>  
 <span data-ttu-id="f6b4d-112">Esta devolución de llamada se controla estableciendo la marca de máscara de eventos [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) al llamar al método [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f6b4d-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="f6b4d-113">Si el generador de perfiles se registra para el método de devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , el tiempo de ejecución pasa la ruta de acceso y el nombre del ensamblado que se va a cargar, junto con un puntero a un objeto de interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a ese método.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="f6b4d-114">Después, el generador de perfiles puede llamar al método [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un objeto `COR_PRF_ASSEMBLY_REFERENCE_INFO` por cada ensamblado de destino al que se va a hacer referencia desde el ensamblado especificado en la devolución de llamada de `GetAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="f6b4d-115">Use la devolución de llamada `GetAssemblyReferences` solo si el generador de perfiles tiene que modificar los metadatos de un ensamblado para agregar referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="f6b4d-116">(Pero tenga en cuenta que la modificación real de los metadatos de un ensamblado se realiza en el método de devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)). El generador de perfiles debe implementar el método de devolución de llamada `GetAssemblyReferences` para informar al Common Language Runtime (CLR) que se agregarán referencias de ensamblado cuando se haya cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="f6b4d-117">Esto garantiza que las decisiones que tome CLR acerca del uso compartido de ensamblados en esta fase temprana seguirán siendo válidas aunque el generador de perfiles tenga planeado modificar las referencias de ensamblado de metadatos más adelante.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="f6b4d-118">De esta manera se pueden evitar algunas instancias en las que las modificaciones de los metadatos del generador de perfiles provocan un error `SECURITY_E_INCOMPATIBLE_SHARE`.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="f6b4d-119">El generador de perfiles usa el objeto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) proporcionado por este método para agregar referencias de ensamblado al rastreador de cierre de referencia de ensamblado de CLR.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="f6b4d-120">El objeto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) solo debe usarse desde esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-120">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="f6b4d-121">Las llamadas al método [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) desde esta devolución de llamada no dan como resultado metadatos modificados, sino solo en un recorrido de cierre de referencia de ensamblado modificado.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="f6b4d-122">El generador de perfiles todavía tendrá que usar un objeto [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) para agregar explícitamente las referencias de ensamblado desde dentro de la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) para el ensamblado de referencia, aunque implemente la devolución de llamada de `GetAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="f6b4d-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="f6b4d-123">El generador de perfiles debe estar preparado para recibir llamadas duplicadas a esta devolución de llamada para el mismo ensamblado y debe responder de forma idéntica para cada una de estas llamadas duplicadas (realizando el mismo conjunto de llamadas a [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="f6b4d-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6b4d-124">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f6b4d-124">Requirements</span></span>  
 <span data-ttu-id="f6b4d-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6b4d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b4d-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6b4d-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6b4d-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6b4d-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6b4d-128">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b4d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b4d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6b4d-129">See also</span></span>

- [<span data-ttu-id="f6b4d-130">ICorProfilerCallback6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6b4d-130">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)
- [<span data-ttu-id="f6b4d-131">ModuleLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="f6b4d-131">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="f6b4d-132">COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="f6b4d-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="f6b4d-133">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6b4d-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
