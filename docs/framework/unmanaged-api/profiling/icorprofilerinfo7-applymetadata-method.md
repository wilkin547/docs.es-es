---
title: 'Icorprofilerinfo7:: Applymetadata (método)'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f261b02dd19ead0d6803cae543f39a06c99f033
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586697"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="4da08-102">Icorprofilerinfo7:: Applymetadata (método)</span><span class="sxs-lookup"><span data-stu-id="4da08-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="4da08-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="4da08-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="4da08-104">Se aplica a los metadatos recién definido por el `IMetadataEmit::Define*` métodos a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="4da08-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da08-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4da08-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4da08-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4da08-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="4da08-107">[in] El identificador del módulo cuyos metadatos se ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="4da08-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4da08-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4da08-108">Remarks</span></span>  
 <span data-ttu-id="4da08-109">Si se realizan cambios en los metadatos después de la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada, debe llamar a este método antes de usar los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="4da08-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="4da08-110">`ApplyMetaData` solo admite la adición de los siguientes tipos de metadatos:</span><span class="sxs-lookup"><span data-stu-id="4da08-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="4da08-111">`AssemblyRef` los registros, que se creación mediante una llamada a la [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="4da08-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="4da08-112">.</span><span class="sxs-lookup"><span data-stu-id="4da08-112">method.</span></span>  
  
- <span data-ttu-id="4da08-113">`TypeRef` los registros, que se creación mediante una llamada a la [DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4da08-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="4da08-114">`TypeSpec` los registros, que se creación mediante una llamada a la [GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4da08-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="4da08-115">`MemberRef` los registros, que se creación mediante una llamada a la [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4da08-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="4da08-116">`MemberSpec` los registros, que se creación mediante una llamada a la [Imetadataemit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4da08-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="4da08-117">`UserString` los registros, que se creación mediante una llamada a la [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4da08-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="4da08-118">A partir de .NET Core 3.0, `ApplyMetaData` también admite los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="4da08-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="4da08-119">`TypeDef` los registros, que se creación mediante una llamada a la [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4da08-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="4da08-120">`MethodDef` los registros, que se creación mediante una llamada a la [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4da08-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="4da08-121">Sin embargo, no se admite la adición de métodos virtuales a un tipo existente.</span><span class="sxs-lookup"><span data-stu-id="4da08-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="4da08-122">Los métodos virtuales deben agregarse antes de la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="4da08-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="4da08-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4da08-123">Requirements</span></span>  
 <span data-ttu-id="4da08-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4da08-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4da08-125">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4da08-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4da08-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4da08-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4da08-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4da08-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da08-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4da08-128">See also</span></span>

- [<span data-ttu-id="4da08-129">ICorProfilerInfo7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4da08-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
