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
ms.openlocfilehash: 6d0f9a8c5c3baf7594e098a3d5544bad55fdc917
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009293"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="c04f9-102">IMetaDataEmit::DeleteFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="c04f9-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="c04f9-103">Destruye la firma de metadatos de serialización de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="c04f9-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c04f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c04f9-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c04f9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c04f9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c04f9-106">de Un `mdFieldDef` `mdParamDef` token o que representa el campo o el parámetro para el que se va a eliminar la firma de metadatos de serialización.</span><span class="sxs-lookup"><span data-stu-id="c04f9-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c04f9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c04f9-107">Requirements</span></span>  
 <span data-ttu-id="c04f9-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c04f9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c04f9-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c04f9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c04f9-110">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c04f9-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c04f9-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c04f9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c04f9-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c04f9-112">See also</span></span>

- [<span data-ttu-id="c04f9-113">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c04f9-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c04f9-114">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c04f9-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
