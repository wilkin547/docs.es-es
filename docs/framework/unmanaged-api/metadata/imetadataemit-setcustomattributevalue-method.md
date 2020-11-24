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
ms.openlocfilehash: c4ea325a755ed05eed378d9201068de31ca8114f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681590"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="3c9d3-102">IMetaDataEmit::SetCustomAttributeValue (Método)</span><span class="sxs-lookup"><span data-stu-id="3c9d3-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>

<span data-ttu-id="3c9d3-103">Establece o actualiza el valor de un atributo personalizado definido por una llamada anterior a [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="3c9d3-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c9d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c9d3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c9d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c9d3-105">Parameters</span></span>  

 `pcv`  
 <span data-ttu-id="3c9d3-106">de Token del atributo personalizado de destino.</span><span class="sxs-lookup"><span data-stu-id="3c9d3-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="3c9d3-107">de Puntero a la matriz que contiene el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="3c9d3-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="3c9d3-108">de Tamaño, en bytes, del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="3c9d3-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c9d3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c9d3-109">Requirements</span></span>  

 <span data-ttu-id="3c9d3-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c9d3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c9d3-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3c9d3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c9d3-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c9d3-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c9d3-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c9d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9d3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c9d3-114">See also</span></span>

- [<span data-ttu-id="3c9d3-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c9d3-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3c9d3-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c9d3-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
