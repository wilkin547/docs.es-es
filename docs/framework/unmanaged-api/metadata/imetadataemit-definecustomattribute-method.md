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
ms.openlocfilehash: 9c4ed282e259aa46fc0cb0175214dc51d3d5fbee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175894"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="ae7fc-102">IMetaDataEmit::DefineCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="ae7fc-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="ae7fc-103">Crea una definición para un atributo personalizado con la firma de metadatos especificada, que se va a asociar al objeto especificado y obtiene un token a esa definición de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="ae7fc-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae7fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae7fc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae7fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae7fc-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="ae7fc-106">[en] El token para el elemento de propietario.</span><span class="sxs-lookup"><span data-stu-id="ae7fc-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ae7fc-107">[en] El token que identifica el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="ae7fc-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="ae7fc-108">[en] Un puntero al atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="ae7fc-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="ae7fc-109">[en] El recuento de `pCustomAttribute`bytes en .</span><span class="sxs-lookup"><span data-stu-id="ae7fc-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="ae7fc-110">[fuera] El `mdCustomAttribute` token asignado.</span><span class="sxs-lookup"><span data-stu-id="ae7fc-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae7fc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae7fc-111">Requirements</span></span>  
 <span data-ttu-id="ae7fc-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae7fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae7fc-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ae7fc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae7fc-114">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae7fc-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae7fc-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae7fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7fc-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae7fc-116">See also</span></span>

- [<span data-ttu-id="ae7fc-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae7fc-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ae7fc-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae7fc-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
