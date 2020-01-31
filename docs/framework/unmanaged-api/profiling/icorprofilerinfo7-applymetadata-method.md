---
title: 'ICorProfilerInfo7:: ApplyMetaData (método)'
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
ms.openlocfilehash: b9e488a512ad506a8975bfff44ae02cd84c29f74
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861702"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="06e9c-102">ICorProfilerInfo7:: ApplyMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="06e9c-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="06e9c-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="06e9c-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="06e9c-104">Aplica los metadatos recién definidos por los métodos `IMetadataEmit::Define*` a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="06e9c-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e9c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06e9c-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06e9c-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="06e9c-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="06e9c-107">de Identificador del módulo cuyos metadatos se cambiaron.</span><span class="sxs-lookup"><span data-stu-id="06e9c-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06e9c-108">Notas</span><span class="sxs-lookup"><span data-stu-id="06e9c-108">Remarks</span></span>  
 <span data-ttu-id="06e9c-109">Si se realizan cambios en los metadatos después de la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , debe llamar a este método antes de usar los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="06e9c-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="06e9c-110">`ApplyMetaData` solo admite agregar los siguientes tipos de metadatos:</span><span class="sxs-lookup"><span data-stu-id="06e9c-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="06e9c-111">`AssemblyRef` registros, que se crean mediante una llamada a [IMetaDataAssemblyEmit::D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="06e9c-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="06e9c-112">.</span><span class="sxs-lookup"><span data-stu-id="06e9c-112">method.</span></span>  
  
- <span data-ttu-id="06e9c-113">`TypeRef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="06e9c-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="06e9c-114">`TypeSpec` registros, que se crean mediante una llamada al método [IMetaDataEmit:: GetTokenFromTypeSpec (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="06e9c-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="06e9c-115">`MemberRef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="06e9c-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="06e9c-116">`MemberSpec` registros, que se crean mediante una llamada al método [IMetaDataEmit2::D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="06e9c-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="06e9c-117">`UserString` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="06e9c-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="06e9c-118">A partir de .NET Core 3,0, `ApplyMetaData` también admite los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="06e9c-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="06e9c-119">`TypeDef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) .</span><span class="sxs-lookup"><span data-stu-id="06e9c-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="06e9c-120">`MethodDef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) .</span><span class="sxs-lookup"><span data-stu-id="06e9c-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="06e9c-121">Sin embargo, no se admite la adición de métodos virtuales a un tipo existente.</span><span class="sxs-lookup"><span data-stu-id="06e9c-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="06e9c-122">Los métodos virtuales deben agregarse antes de la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="06e9c-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="06e9c-123">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="06e9c-123">Requirements</span></span>  
 <span data-ttu-id="06e9c-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06e9c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06e9c-125">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06e9c-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06e9c-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06e9c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06e9c-127">**.NET Framework versiones:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06e9c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e9c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="06e9c-128">See also</span></span>

- [<span data-ttu-id="06e9c-129">ICorProfilerInfo7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06e9c-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
