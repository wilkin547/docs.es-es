---
description: 'Más información sobre: IMetaDataEmit:: Settypedefprops ((método)'
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
ms.openlocfilehash: 1160d20e7ceb422390f8cd725a75fdb4f42318e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706505"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="a49e8-103">IMetaDataEmit::SetTypeDefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="a49e8-103">IMetaDataEmit::SetTypeDefProps Method</span></span>

<span data-ttu-id="a49e8-104">Establece las características de un tipo definido por una llamada anterior a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="a49e8-104">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a49e8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a49e8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a49e8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a49e8-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="a49e8-107">de Un `mdTypeDef` token Obtenido de la llamada original a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="a49e8-107">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="a49e8-108">[in] `TypeDef` sus.</span><span class="sxs-lookup"><span data-stu-id="a49e8-108">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="a49e8-109">Se trata de una máscara de máscara de `CorTypeAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="a49e8-109">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="a49e8-110">de `mdToken` De la clase base.</span><span class="sxs-lookup"><span data-stu-id="a49e8-110">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="a49e8-111">Se obtiene de una llamada anterior a [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md), o `null` .</span><span class="sxs-lookup"><span data-stu-id="a49e8-111">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="a49e8-112">de Matriz de tokens para las interfaces que este tipo implementa.</span><span class="sxs-lookup"><span data-stu-id="a49e8-112">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="a49e8-113">Estos `mdTypeRef` tokens se obtienen mediante [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="a49e8-113">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="a49e8-114">El último elemento de la matriz debe ser `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="a49e8-114">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a49e8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a49e8-115">Requirements</span></span>  

 <span data-ttu-id="a49e8-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a49e8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a49e8-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a49e8-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a49e8-118">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a49e8-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a49e8-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a49e8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49e8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a49e8-120">See also</span></span>

- [<span data-ttu-id="a49e8-121">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a49e8-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a49e8-122">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a49e8-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
