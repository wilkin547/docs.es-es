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
ms.openlocfilehash: 2f572f66f16ff701350fde3b05be822b9e8c78b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706839"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="858d9-102">IMetaDataEmit::SetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="858d9-102">IMetaDataEmit::SetTypeDefProps Method</span></span>

<span data-ttu-id="858d9-103">Establece las características de un tipo definido por una llamada anterior a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="858d9-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="858d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="858d9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="858d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="858d9-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="858d9-106">de Un `mdTypeDef` token Obtenido de la llamada original a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="858d9-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="858d9-107">[in] `TypeDef` sus.</span><span class="sxs-lookup"><span data-stu-id="858d9-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="858d9-108">Se trata de una máscara de máscara de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="858d9-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="858d9-109">de `mdToken` De la clase base.</span><span class="sxs-lookup"><span data-stu-id="858d9-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="858d9-110">Se obtiene de una llamada anterior a [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md), o `null` .</span><span class="sxs-lookup"><span data-stu-id="858d9-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="858d9-111">de Matriz de tokens para las interfaces que este tipo implementa.</span><span class="sxs-lookup"><span data-stu-id="858d9-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="858d9-112">Estos `mdTypeRef` tokens se obtienen mediante [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="858d9-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="858d9-113">El último elemento de la matriz debe ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="858d9-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="858d9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="858d9-114">Requirements</span></span>  

 <span data-ttu-id="858d9-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="858d9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="858d9-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="858d9-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="858d9-117">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="858d9-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="858d9-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="858d9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="858d9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="858d9-119">See also</span></span>

- [<span data-ttu-id="858d9-120">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="858d9-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="858d9-121">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="858d9-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
