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
ms.openlocfilehash: c30206145d08a22af49c4a6a0dc83fd7382bcc06
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495514"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="5c8a0-102">ICorProfilerInfo7:: ApplyMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="5c8a0-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="5c8a0-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="5c8a0-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="5c8a0-104">Aplica los metadatos recién definidos por los `IMetadataEmit::Define*` métodos a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="5c8a0-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c8a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c8a0-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c8a0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c8a0-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="5c8a0-107">de Identificador del módulo cuyos metadatos se cambiaron.</span><span class="sxs-lookup"><span data-stu-id="5c8a0-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c8a0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c8a0-108">Remarks</span></span>  
 <span data-ttu-id="5c8a0-109">Si se realizan cambios en los metadatos después de la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , debe llamar a este método antes de usar los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="5c8a0-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="5c8a0-110">`ApplyMetaData`solo admite la adición de los siguientes tipos de metadatos:</span><span class="sxs-lookup"><span data-stu-id="5c8a0-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="5c8a0-111">`AssemblyRef`registros, que se crean mediante una llamada a [IMetaDataAssemblyEmit::D efineassemblyref](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="5c8a0-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="5c8a0-112">.</span><span class="sxs-lookup"><span data-stu-id="5c8a0-112">method.</span></span>  
  
- <span data-ttu-id="5c8a0-113">`TypeRef`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8a0-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="5c8a0-114">`TypeSpec`registros, que se crean mediante una llamada al método [IMetaDataEmit:: GetTokenFromTypeSpec (](../metadata/imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8a0-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="5c8a0-115">`MemberRef`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinememberref](../metadata/imetadataemit-definememberref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8a0-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="5c8a0-116">`MemberSpec`registros, que se crean mediante una llamada al método [IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8a0-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="5c8a0-117">`UserString`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efineuserstring](../metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8a0-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="5c8a0-118">A partir de .NET Core 3,0, `ApplyMetaData` también admite los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="5c8a0-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="5c8a0-119">`TypeDef`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetypedef](../metadata/imetadataemit-definetypedef-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8a0-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="5c8a0-120">`MethodDef`registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8a0-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="5c8a0-121">Sin embargo, no se admite la adición de métodos virtuales a un tipo existente.</span><span class="sxs-lookup"><span data-stu-id="5c8a0-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="5c8a0-122">Los métodos virtuales deben agregarse antes de la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5c8a0-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c8a0-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c8a0-123">Requirements</span></span>  
 <span data-ttu-id="5c8a0-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c8a0-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c8a0-125">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c8a0-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c8a0-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c8a0-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c8a0-127">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c8a0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c8a0-128">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="5c8a0-128">See also</span></span>

- [<span data-ttu-id="5c8a0-129">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="5c8a0-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
