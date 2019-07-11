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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b64275def01d7b62f9a461de69a286769094305e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777585"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="fb977-102">IMetaDataEmit::DefineMethodImpl (Método)</span><span class="sxs-lookup"><span data-stu-id="fb977-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="fb977-103">Crea una definición para la implementación de un método heredado de una interfaz y devuelve un token para esa definición de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="fb977-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb977-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb977-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb977-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb977-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="fb977-106">[in] El `mdTypedef` símbolo (token) de la clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="fb977-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="fb977-107">[in] El `mdMethodDef` o `mdMemberRef` símbolo (token) del cuerpo del código.</span><span class="sxs-lookup"><span data-stu-id="fb977-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="fb977-108">[in] El `mdMethodDef` o `mdMemberRef` token del método de interfaz que se implementan.</span><span class="sxs-lookup"><span data-stu-id="fb977-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb977-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb977-109">Requirements</span></span>  
 <span data-ttu-id="fb977-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb977-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb977-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb977-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb977-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb977-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb977-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb977-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb977-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb977-114">See also</span></span>

- [<span data-ttu-id="fb977-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb977-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fb977-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb977-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
