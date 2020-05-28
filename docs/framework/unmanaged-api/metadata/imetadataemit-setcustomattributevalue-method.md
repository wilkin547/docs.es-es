---
title: IMetaDataEmit::SetCustomAttributeValue (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: 6e24db7da7abbdb597b8ff64515e8053667af3ff
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008773"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="d1aef-102">IMetaDataEmit::SetCustomAttributeValue (Método)</span><span class="sxs-lookup"><span data-stu-id="d1aef-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="d1aef-103">Establece o actualiza el valor de un atributo personalizado definido por una llamada anterior a [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="d1aef-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1aef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1aef-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1aef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1aef-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="d1aef-106">de Token del atributo personalizado de destino.</span><span class="sxs-lookup"><span data-stu-id="d1aef-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="d1aef-107">de Puntero a la matriz que contiene el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="d1aef-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="d1aef-108">de Tamaño, en bytes, del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="d1aef-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1aef-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1aef-109">Requirements</span></span>  
 <span data-ttu-id="d1aef-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1aef-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1aef-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d1aef-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1aef-112">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d1aef-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1aef-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1aef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1aef-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1aef-114">See also</span></span>

- [<span data-ttu-id="d1aef-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1aef-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d1aef-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1aef-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
