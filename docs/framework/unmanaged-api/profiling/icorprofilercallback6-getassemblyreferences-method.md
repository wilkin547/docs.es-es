---
description: 'Más información sobre: ICorProfilerCallback6:: GetAssemblyReferences (método)'
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
ms.openlocfilehash: 27c2b5e0ed935501de551bac32b6d229d5c59f79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788649"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="7be62-103">ICorProfilerCallback6::GetAssemblyReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="7be62-103">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>

<span data-ttu-id="7be62-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="7be62-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="7be62-105">Notifica al generador de perfiles que un ensamblado está en una etapa de carga muy temprana, cuando Common Language Runtime realiza un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7be62-105">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be62-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7be62-106">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7be62-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7be62-107">Parameters</span></span>  

 `wszAssemblyPath`  
 <span data-ttu-id="7be62-108">[in] Ruta de acceso y nombre del ensamblado cuyos metadatos se modificarán.</span><span class="sxs-lookup"><span data-stu-id="7be62-108">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="7be62-109">de Puntero a la dirección de una interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) que especifica las referencias de ensamblado que se van a agregar.</span><span class="sxs-lookup"><span data-stu-id="7be62-109">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7be62-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7be62-110">Return Value</span></span>  

 <span data-ttu-id="7be62-111">Los valores devueltos de esta devolución de llamada se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="7be62-111">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7be62-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7be62-112">Remarks</span></span>  

 <span data-ttu-id="7be62-113">Esta devolución de llamada se controla estableciendo la marca de máscara de eventos [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) al llamar al método [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7be62-113">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="7be62-114">Si el generador de perfiles se registra para el método de devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , el tiempo de ejecución pasa la ruta de acceso y el nombre del ensamblado que se va a cargar, junto con un puntero a un objeto de interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a ese método.</span><span class="sxs-lookup"><span data-stu-id="7be62-114">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="7be62-115">Después, el generador de perfiles puede llamar al método [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` objeto para cada ensamblado de destino al que tiene previsto hacer referencia desde el ensamblado especificado en la `GetAssemblyReferences` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="7be62-115">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="7be62-116">Use la devolución de llamada `GetAssemblyReferences` solo si el generador de perfiles tiene que modificar los metadatos de un ensamblado para agregar referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7be62-116">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="7be62-117">(Pero tenga en cuenta que la modificación real de los metadatos de un ensamblado se realiza en el método de devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)). El generador de perfiles debe implementar el `GetAssemblyReferences` método de devolución de llamada para informar al Common Language Runtime (CLR) que se agregarán referencias de ensamblado cuando se haya cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="7be62-117">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="7be62-118">Esto garantiza que las decisiones que tome CLR acerca del uso compartido de ensamblados en esta fase temprana seguirán siendo válidas aunque el generador de perfiles tenga planeado modificar las referencias de ensamblado de metadatos más adelante.</span><span class="sxs-lookup"><span data-stu-id="7be62-118">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="7be62-119">De esta manera se pueden evitar algunas instancias en las que las modificaciones de los metadatos del generador de perfiles provocan un error `SECURITY_E_INCOMPATIBLE_SHARE`.</span><span class="sxs-lookup"><span data-stu-id="7be62-119">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="7be62-120">El generador de perfiles usa el objeto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) proporcionado por este método para agregar referencias de ensamblado al rastreador de cierre de referencia de ensamblado de CLR.</span><span class="sxs-lookup"><span data-stu-id="7be62-120">The profiler uses the [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="7be62-121">El objeto [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) solo debe usarse desde esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="7be62-121">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="7be62-122">Las llamadas al método [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) desde esta devolución de llamada no dan como resultado metadatos modificados, sino solo en un recorrido de cierre de referencia de ensamblado modificado.</span><span class="sxs-lookup"><span data-stu-id="7be62-122">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="7be62-123">El generador de perfiles todavía tendrá que usar un objeto [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) para agregar explícitamente las referencias de ensamblado desde dentro de la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) para el ensamblado de referencia, aunque implemente la `GetAssemblyReferences` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="7be62-123">The profiler will still have to use an [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="7be62-124">El generador de perfiles debe estar preparado para recibir llamadas duplicadas a esta devolución de llamada para el mismo ensamblado y debe responder de forma idéntica para cada una de estas llamadas duplicadas (realizando el mismo conjunto de llamadas a [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) ).</span><span class="sxs-lookup"><span data-stu-id="7be62-124">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be62-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7be62-125">Requirements</span></span>  

 <span data-ttu-id="7be62-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be62-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be62-127">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7be62-127">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7be62-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be62-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be62-129">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be62-129">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be62-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7be62-130">See also</span></span>

- [<span data-ttu-id="7be62-131">ICorProfilerCallback6 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7be62-131">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)
- [<span data-ttu-id="7be62-132">Método ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="7be62-132">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="7be62-133">COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)</span><span class="sxs-lookup"><span data-stu-id="7be62-133">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="7be62-134">ICorProfilerAssemblyReferenceProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7be62-134">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
