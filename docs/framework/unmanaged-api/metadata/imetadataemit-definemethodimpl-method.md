---
title: "IMetaDataEmit::DefineMethodImpl (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5bf16c51a241a01f18aae84f8b3bb7554f08b87c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="0c515-102">IMetaDataEmit::DefineMethodImpl (Método)</span><span class="sxs-lookup"><span data-stu-id="0c515-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="0c515-103">Crea una definición para la implementación de un método que se hereda de una interfaz y devuelve un token para que la definición de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="0c515-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c515-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c515-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c515-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c515-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0c515-106">[in] El `mdTypedef` símbolo (token) de la clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="0c515-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="0c515-107">[in] El `mdMethodDef` o `mdMethodRef` símbolo (token) del cuerpo del código.</span><span class="sxs-lookup"><span data-stu-id="0c515-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="0c515-108">[in] El `mdMethodDef` o `mdMethodRef` símbolo (token) del método de interfaz que se están implementando.</span><span class="sxs-lookup"><span data-stu-id="0c515-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c515-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c515-109">Requirements</span></span>  
 <span data-ttu-id="0c515-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c515-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c515-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c515-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c515-112">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c515-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c515-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c515-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c515-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c515-114">See Also</span></span>  
 [<span data-ttu-id="0c515-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c515-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0c515-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c515-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
