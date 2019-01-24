---
title: IMetaDataEmit::DeleteFieldMarshal (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e7ba2d6f143b6bbb9ddc5a056191e53f719bfeb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643954"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="67afa-102">IMetaDataEmit::DeleteFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="67afa-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="67afa-103">Destruye la firma de metadatos para el objeto al que hace referencia el token especificado de cálculo de referencias de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="67afa-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67afa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67afa-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67afa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67afa-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="67afa-106">[in] Un `mdFieldDef` o `mdParamDef` token que representa el campo o parámetro que se va a eliminar la firma de metadatos de cálculo de referencias.</span><span class="sxs-lookup"><span data-stu-id="67afa-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67afa-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67afa-107">Requirements</span></span>  
 <span data-ttu-id="67afa-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67afa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67afa-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="67afa-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67afa-110">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67afa-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67afa-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67afa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67afa-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="67afa-112">See also</span></span>
- [<span data-ttu-id="67afa-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67afa-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="67afa-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67afa-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
