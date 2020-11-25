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
ms.openlocfilehash: 5989c45782b4f83ecfa285cb305080320abf6a3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700553"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="f389b-102">IMetaDataEmit::DeleteFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="f389b-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>

<span data-ttu-id="f389b-103">Destruye la firma de metadatos de serialización de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="f389b-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f389b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f389b-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f389b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f389b-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="f389b-106">de Un `mdFieldDef` `mdParamDef` token o que representa el campo o el parámetro para el que se va a eliminar la firma de metadatos de serialización.</span><span class="sxs-lookup"><span data-stu-id="f389b-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f389b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f389b-107">Requirements</span></span>  

 <span data-ttu-id="f389b-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f389b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f389b-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f389b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f389b-110">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f389b-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f389b-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f389b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f389b-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f389b-112">See also</span></span>

- [<span data-ttu-id="f389b-113">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f389b-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f389b-114">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f389b-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
