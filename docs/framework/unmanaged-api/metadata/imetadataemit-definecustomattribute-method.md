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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 994e007eabf8b7fdcf5446d905c06eb4ab91bb3f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777681"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="83b48-102">IMetaDataEmit::DefineCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="83b48-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="83b48-103">Crea una definición para un atributo personalizado con la firma de metadatos especificado, que se adjuntará al objeto especificado y obtiene un token para esa definición de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="83b48-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b48-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83b48-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83b48-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83b48-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="83b48-106">[in] El token para el elemento de propietario.</span><span class="sxs-lookup"><span data-stu-id="83b48-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="83b48-107">[in] El token que identifica el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="83b48-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="83b48-108">[in] Un puntero al atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="83b48-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="83b48-109">[in] El recuento de bytes en `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="83b48-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="83b48-110">[out] El `mdCustomAttribute` token asignado.</span><span class="sxs-lookup"><span data-stu-id="83b48-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b48-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83b48-111">Requirements</span></span>  
 <span data-ttu-id="83b48-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83b48-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83b48-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="83b48-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83b48-114">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83b48-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83b48-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83b48-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b48-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="83b48-116">See also</span></span>

- [<span data-ttu-id="83b48-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83b48-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="83b48-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83b48-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
