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
ms.openlocfilehash: 64d76efa8c2f29fda559e5c84217b865540027ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175829"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="2bc3d-102">IMetaDataEmit::DefineMethodImpl (Método)</span><span class="sxs-lookup"><span data-stu-id="2bc3d-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="2bc3d-103">Crea una definición para la implementación de un método heredado de una interfaz y devuelve un token a esa definición de implementación de método.</span><span class="sxs-lookup"><span data-stu-id="2bc3d-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc3d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bc3d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc3d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bc3d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2bc3d-106">[en] El `mdTypedef` token de la clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="2bc3d-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="2bc3d-107">[en] El `mdMethodDef` `mdMemberRef` token o del cuerpo del código.</span><span class="sxs-lookup"><span data-stu-id="2bc3d-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="2bc3d-108">[en] El `mdMethodDef` `mdMemberRef` token o del método de interfaz que se está implementando.</span><span class="sxs-lookup"><span data-stu-id="2bc3d-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc3d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bc3d-109">Requirements</span></span>  
 <span data-ttu-id="2bc3d-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bc3d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bc3d-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2bc3d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bc3d-112">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2bc3d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bc3d-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc3d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc3d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bc3d-114">See also</span></span>

- [<span data-ttu-id="2bc3d-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bc3d-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2bc3d-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bc3d-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
