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
ms.openlocfilehash: b05527f118de059c674ea659b1a22b7895126cf4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007772"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="06bd6-102">IMetaDataEmit::SetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="06bd6-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="06bd6-103">Establece las características de un tipo definido por una llamada anterior a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="06bd6-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06bd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06bd6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06bd6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06bd6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="06bd6-106">de Un `mdTypeDef` token Obtenido de la llamada original a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="06bd6-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="06bd6-107">[in] `TypeDef` sus.</span><span class="sxs-lookup"><span data-stu-id="06bd6-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="06bd6-108">Se trata de una máscara de máscara de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="06bd6-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="06bd6-109">de `mdToken`De la clase base.</span><span class="sxs-lookup"><span data-stu-id="06bd6-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="06bd6-110">Se obtiene de una llamada anterior a [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md), o `null` .</span><span class="sxs-lookup"><span data-stu-id="06bd6-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="06bd6-111">de Matriz de tokens para las interfaces que este tipo implementa.</span><span class="sxs-lookup"><span data-stu-id="06bd6-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="06bd6-112">Estos `mdTypeRef` tokens se obtienen mediante [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="06bd6-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="06bd6-113">El último elemento de la matriz debe ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="06bd6-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06bd6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06bd6-114">Requirements</span></span>  
 <span data-ttu-id="06bd6-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06bd6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06bd6-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06bd6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06bd6-117">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06bd6-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06bd6-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06bd6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06bd6-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06bd6-119">See also</span></span>

- [<span data-ttu-id="06bd6-120">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06bd6-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="06bd6-121">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06bd6-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
