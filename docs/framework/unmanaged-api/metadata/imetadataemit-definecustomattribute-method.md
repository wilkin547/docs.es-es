---
title: IMetaDataEmit::DefineCustomAttribute (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: 096a460f9d6581ebdd00f8487af68f652524d52f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681670"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="a904f-102">IMetaDataEmit::DefineCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="a904f-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>

<span data-ttu-id="a904f-103">Crea una definición para un atributo personalizado con la firma de metadatos especificada, que se va a adjuntar al objeto especificado y obtiene un token para esa definición de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a904f-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a904f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a904f-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a904f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a904f-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="a904f-106">de El token del elemento de propietario.</span><span class="sxs-lookup"><span data-stu-id="a904f-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="a904f-107">de El token que identifica el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a904f-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="a904f-108">de Puntero al atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="a904f-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="a904f-109">de Recuento de bytes de `pCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="a904f-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="a904f-110">enuncia El `mdCustomAttribute` token asignado.</span><span class="sxs-lookup"><span data-stu-id="a904f-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a904f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a904f-111">Requirements</span></span>  

 <span data-ttu-id="a904f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a904f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a904f-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a904f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a904f-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a904f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a904f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a904f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a904f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a904f-116">See also</span></span>

- [<span data-ttu-id="a904f-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a904f-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a904f-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a904f-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
