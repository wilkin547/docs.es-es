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
ms.openlocfilehash: 17757df566ba8d141e7adec00dcc1f75959d0e00
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005634"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="6b0b0-102">IMetaDataEmit::DefineCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="6b0b0-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="6b0b0-103">Crea una definición para un atributo personalizado con la firma de metadatos especificada, que se va a adjuntar al objeto especificado y obtiene un token para esa definición de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6b0b0-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b0b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b0b0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b0b0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b0b0-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="6b0b0-106">de El token del elemento de propietario.</span><span class="sxs-lookup"><span data-stu-id="6b0b0-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="6b0b0-107">de El token que identifica el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6b0b0-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="6b0b0-108">de Puntero al atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6b0b0-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="6b0b0-109">de Recuento de bytes de `pCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="6b0b0-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="6b0b0-110">enuncia El `mdCustomAttribute` token asignado.</span><span class="sxs-lookup"><span data-stu-id="6b0b0-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b0b0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b0b0-111">Requirements</span></span>  
 <span data-ttu-id="6b0b0-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b0b0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b0b0-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6b0b0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b0b0-114">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6b0b0-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b0b0-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b0b0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b0b0-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b0b0-116">See also</span></span>

- [<span data-ttu-id="6b0b0-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b0b0-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6b0b0-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b0b0-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
