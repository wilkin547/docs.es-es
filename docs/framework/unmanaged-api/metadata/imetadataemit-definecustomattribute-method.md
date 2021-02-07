---
description: 'Más información acerca de: IMetaDataEmit::D método efineCustomAttribute'
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
ms.openlocfilehash: 5d802f590525b8b398ac270b1b7f59d122b45b73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753489"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="caa1c-103">IMetaDataEmit::DefineCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="caa1c-103">IMetaDataEmit::DefineCustomAttribute Method</span></span>

<span data-ttu-id="caa1c-104">Crea una definición para un atributo personalizado con la firma de metadatos especificada, que se va a adjuntar al objeto especificado y obtiene un token para esa definición de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="caa1c-104">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa1c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="caa1c-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caa1c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="caa1c-106">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="caa1c-107">de El token del elemento de propietario.</span><span class="sxs-lookup"><span data-stu-id="caa1c-107">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="caa1c-108">de El token que identifica el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="caa1c-108">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="caa1c-109">de Puntero al atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="caa1c-109">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="caa1c-110">de Recuento de bytes de `pCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="caa1c-110">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="caa1c-111">enuncia El `mdCustomAttribute` token asignado.</span><span class="sxs-lookup"><span data-stu-id="caa1c-111">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa1c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="caa1c-112">Requirements</span></span>  

 <span data-ttu-id="caa1c-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caa1c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caa1c-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="caa1c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="caa1c-115">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="caa1c-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caa1c-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caa1c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa1c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="caa1c-117">See also</span></span>

- [<span data-ttu-id="caa1c-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa1c-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="caa1c-119">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa1c-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
