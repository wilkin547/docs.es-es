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
ms.openlocfilehash: 78f2405bba9172b775b01e5417860c3f3d2dd4a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206933"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="ba2b2-102">IMetaDataEmit::DeleteFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="ba2b2-103">Destruye la firma de metadatos para el objeto al que hace referencia el token especificado de cálculo de referencias de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba2b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba2b2-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba2b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba2b2-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ba2b2-106">[in] Un `mdFieldDef` o `mdParamDef` token que representa el campo o parámetro que se va a eliminar la firma de metadatos de cálculo de referencias.</span><span class="sxs-lookup"><span data-stu-id="ba2b2-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba2b2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba2b2-107">Requirements</span></span>  
 <span data-ttu-id="ba2b2-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba2b2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba2b2-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba2b2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba2b2-110">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba2b2-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba2b2-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba2b2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba2b2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba2b2-112">See also</span></span>

- [<span data-ttu-id="ba2b2-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ba2b2-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba2b2-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
