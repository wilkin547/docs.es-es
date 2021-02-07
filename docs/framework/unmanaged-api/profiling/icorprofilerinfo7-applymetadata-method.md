---
description: 'Más información sobre: ICorProfilerInfo7:: ApplyMetaData (método)'
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
ms.openlocfilehash: 3a4554357ede85d936e8bf9c87c6b9c096dab188
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737134"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="394be-103">ICorProfilerInfo7:: ApplyMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="394be-103">ICorProfilerInfo7::ApplyMetaData Method</span></span>

<span data-ttu-id="394be-104">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="394be-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="394be-105">Aplica los metadatos recién definidos por los `IMetadataEmit::Define*` métodos a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="394be-105">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="394be-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="394be-106">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="394be-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="394be-107">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="394be-108">de Identificador del módulo cuyos metadatos se cambiaron.</span><span class="sxs-lookup"><span data-stu-id="394be-108">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="394be-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="394be-109">Remarks</span></span>  

 <span data-ttu-id="394be-110">Si se realizan cambios en los metadatos después de la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , debe llamar a este método antes de usar los nuevos metadatos.</span><span class="sxs-lookup"><span data-stu-id="394be-110">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="394be-111">`ApplyMetaData` solo admite la adición de los siguientes tipos de metadatos:</span><span class="sxs-lookup"><span data-stu-id="394be-111">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="394be-112">`AssemblyRef` registros, que se crean mediante una llamada a [IMetaDataAssemblyEmit::D efineassemblyref](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="394be-112">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="394be-113">.</span><span class="sxs-lookup"><span data-stu-id="394be-113">method.</span></span>  
  
- <span data-ttu-id="394be-114">`TypeRef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetyperefbyname](../metadata/imetadataemit-definetyperefbyname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="394be-114">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="394be-115">`TypeSpec` registros, que se crean mediante una llamada al método [IMetaDataEmit:: GetTokenFromTypeSpec (](../metadata/imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="394be-115">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="394be-116">`MemberRef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinememberref](../metadata/imetadataemit-definememberref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="394be-116">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="394be-117">`MemberSpec` registros, que se crean mediante una llamada al método [IMetaDataEmit2::D efinemethodspec](../metadata/imetadataemit2-definemethodspec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="394be-117">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="394be-118">`UserString` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efineuserstring](../metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="394be-118">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="394be-119">A partir de .NET Core 3,0, `ApplyMetaData` también admite los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="394be-119">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="394be-120">`TypeDef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinetypedef](../metadata/imetadataemit-definetypedef-method.md) .</span><span class="sxs-lookup"><span data-stu-id="394be-120">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="394be-121">`MethodDef` registros, que se crean mediante una llamada al método [IMetaDataEmit::D efinemethod](../metadata/imetadataemit-definemethod-method.md) .</span><span class="sxs-lookup"><span data-stu-id="394be-121">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="394be-122">Sin embargo, no se admite la adición de métodos virtuales a un tipo existente.</span><span class="sxs-lookup"><span data-stu-id="394be-122">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="394be-123">Los métodos virtuales deben agregarse antes de la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="394be-123">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="394be-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="394be-124">Requirements</span></span>  

 <span data-ttu-id="394be-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="394be-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="394be-126">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="394be-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="394be-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="394be-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="394be-128">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="394be-128">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="394be-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="394be-129">See also</span></span>

- [<span data-ttu-id="394be-130">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="394be-130">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
