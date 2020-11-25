---
title: IMetaDataEmit::DefineMethodImpl (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
ms.openlocfilehash: 24a7c5bca1287e55f3eb06d63e1fed8da37eb3b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719572"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="bc62a-102">IMetaDataEmit::DefineMethodImpl (Método)</span><span class="sxs-lookup"><span data-stu-id="bc62a-102">IMetaDataEmit::DefineMethodImpl Method</span></span>

<span data-ttu-id="bc62a-103">Crea una definición para la implementación de un método heredado de una interfaz y devuelve un token a esa definición de implementación de método.</span><span class="sxs-lookup"><span data-stu-id="bc62a-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc62a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc62a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc62a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc62a-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="bc62a-106">de `mdTypedef` Token de la clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="bc62a-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="bc62a-107">de El `mdMethodDef` `mdMemberRef` token o del cuerpo del código.</span><span class="sxs-lookup"><span data-stu-id="bc62a-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="bc62a-108">de El `mdMethodDef` `mdMemberRef` token o del método de interfaz que se implementa.</span><span class="sxs-lookup"><span data-stu-id="bc62a-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc62a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc62a-109">Requirements</span></span>  

 <span data-ttu-id="bc62a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc62a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc62a-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bc62a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc62a-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc62a-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc62a-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc62a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc62a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc62a-114">See also</span></span>

- [<span data-ttu-id="bc62a-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc62a-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="bc62a-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc62a-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
