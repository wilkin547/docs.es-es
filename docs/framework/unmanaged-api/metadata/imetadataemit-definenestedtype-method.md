---
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
ms.openlocfilehash: 99dc141cca0f911c8dd65645f6c22d950cc678d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719546"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="a52ac-102">IMetaDataEmit::DefineNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="a52ac-102">IMetaDataEmit::DefineNestedType Method</span></span>

<span data-ttu-id="a52ac-103">Crea la firma de metadatos de una definición de tipo, devuelve un `mdTypeDef` token para ese tipo y especifica que el tipo definido es un miembro del tipo al que hace referencia el `tdEncloser` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a52ac-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a52ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a52ac-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a52ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a52ac-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="a52ac-106">de Nombre del tipo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="a52ac-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="a52ac-107">[in] `TypeDef` sus.</span><span class="sxs-lookup"><span data-stu-id="a52ac-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="a52ac-108">Se trata de una máscara de máscara de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="a52ac-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="a52ac-109">de Token de la clase base.</span><span class="sxs-lookup"><span data-stu-id="a52ac-109">[in] The token of the base class.</span></span> <span data-ttu-id="a52ac-110">Este es un `mdTypeDef` `mdTypeRef` token o.</span><span class="sxs-lookup"><span data-stu-id="a52ac-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="a52ac-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="a52ac-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="a52ac-112">de Matriz de tokens que especifican las interfaces que esta clase o interfaz implementa.</span><span class="sxs-lookup"><span data-stu-id="a52ac-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="a52ac-113">de Token del tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="a52ac-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="a52ac-114">El último elemento de la matriz debe ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="a52ac-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="a52ac-115">enuncia El `mdTypeDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="a52ac-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a52ac-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a52ac-116">Requirements</span></span>  

 <span data-ttu-id="a52ac-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a52ac-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a52ac-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a52ac-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a52ac-119">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a52ac-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a52ac-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a52ac-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52ac-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a52ac-121">See also</span></span>

- [<span data-ttu-id="a52ac-122">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a52ac-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a52ac-123">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a52ac-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
