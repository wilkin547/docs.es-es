---
title: IMetaDataEmit::SetTypeDefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b72088e4aa9994ca6ae411ec36d4c578e3017e5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447888"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="b39c2-102">IMetaDataEmit::SetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b39c2-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="b39c2-103">Establece las características de un tipo definido por una llamada anterior a [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="b39c2-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b39c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b39c2-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b39c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b39c2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b39c2-106">[in] Un `mdTypeDef` token obtenido a partir de la llamada original a [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="b39c2-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="b39c2-107">[in] `TypeDef` atributos.</span><span class="sxs-lookup"><span data-stu-id="b39c2-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="b39c2-108">Se trata de una máscara de bits de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="b39c2-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="b39c2-109">[in] El `mdToken` de la clase base.</span><span class="sxs-lookup"><span data-stu-id="b39c2-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="b39c2-110">Obtenido de una llamada anterior a [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), o `null`.</span><span class="sxs-lookup"><span data-stu-id="b39c2-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="b39c2-111">[in] Una matriz de símbolos (tokens) para las interfaces que implementa este tipo.</span><span class="sxs-lookup"><span data-stu-id="b39c2-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="b39c2-112">Estos `mdTypeRef` símbolos (tokens) se obtiene utilizando [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="b39c2-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="b39c2-113">Es el último elemento de la matriz deben ser `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="b39c2-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b39c2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b39c2-114">Requirements</span></span>  
 <span data-ttu-id="b39c2-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b39c2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b39c2-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b39c2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b39c2-117">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b39c2-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b39c2-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b39c2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b39c2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b39c2-119">See Also</span></span>  
 [<span data-ttu-id="b39c2-120">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b39c2-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b39c2-121">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b39c2-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
