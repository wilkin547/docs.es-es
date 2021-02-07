---
description: 'Más información acerca de: IMetaDataEmit::D método efineNestedType'
title: IMetaDataEmit::DefineNestedType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 1b0c5c8d1bffa425b2019a4434042c84a0069907
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753385"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="88f6d-103">IMetaDataEmit::DefineNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="88f6d-103">IMetaDataEmit::DefineNestedType Method</span></span>

<span data-ttu-id="88f6d-104">Crea la firma de metadatos de una definición de tipo, devuelve un `mdTypeDef` token para ese tipo y especifica que el tipo definido es un miembro del tipo al que hace referencia el `tdEncloser` parámetro.</span><span class="sxs-lookup"><span data-stu-id="88f6d-104">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88f6d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88f6d-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88f6d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88f6d-106">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="88f6d-107">de Nombre del tipo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="88f6d-107">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="88f6d-108">[in] `TypeDef` sus.</span><span class="sxs-lookup"><span data-stu-id="88f6d-108">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="88f6d-109">Se trata de una máscara de máscara de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="88f6d-109">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="88f6d-110">de Token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="88f6d-110">[in] The token of the base class.</span></span> <span data-ttu-id="88f6d-111">Este es un `mdTypeDef` `mdTypeRef` token o.</span><span class="sxs-lookup"><span data-stu-id="88f6d-111">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="88f6d-112">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="88f6d-112">`rtkImplements`[]</span></span>  
 <span data-ttu-id="88f6d-113">de Matriz de tokens que especifican las interfaces que esta clase o interfaz implementa.</span><span class="sxs-lookup"><span data-stu-id="88f6d-113">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="88f6d-114">de Token del tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="88f6d-114">[in] The token of the enclosing type.</span></span> <span data-ttu-id="88f6d-115">El último elemento de la matriz debe ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="88f6d-115">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="88f6d-116">enuncia El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="88f6d-116">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88f6d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88f6d-117">Requirements</span></span>  

 <span data-ttu-id="88f6d-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88f6d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88f6d-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="88f6d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88f6d-120">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88f6d-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88f6d-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88f6d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88f6d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="88f6d-122">See also</span></span>

- [<span data-ttu-id="88f6d-123">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88f6d-123">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="88f6d-124">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88f6d-124">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
