---
title: "IMetaDataEmit::DefineMethodImpl (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethodImpl
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 126cf950b71ed2325006b14927ae95517f7c6dc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="3a3dc-102">IMetaDataEmit::DefineMethodImpl (Método)</span><span class="sxs-lookup"><span data-stu-id="3a3dc-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="3a3dc-103">Crea una definición para la implementación de un método que se hereda de una interfaz y devuelve un token para que la definición de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a3dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a3dc-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a3dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a3dc-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3a3dc-106">[in] El `mdTypedef` símbolo (token) de la clase de implementación.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="3a3dc-107">[in] El `mdMethodDef` o `mdMethodRef` símbolo (token) del cuerpo del código.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="3a3dc-108">[in] El `mdMethodDef` o `mdMethodRef` símbolo (token) del método de interfaz que se están implementando.</span><span class="sxs-lookup"><span data-stu-id="3a3dc-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a3dc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a3dc-109">Requirements</span></span>  
 <span data-ttu-id="3a3dc-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a3dc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a3dc-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a3dc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a3dc-112">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a3dc-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a3dc-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a3dc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a3dc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a3dc-114">See Also</span></span>  
 [<span data-ttu-id="3a3dc-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a3dc-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="3a3dc-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a3dc-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
