---
title: IMetaDataEmit::SetFieldMarshal (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b65f3476da69249f449090e1f2d67c58ed5a427a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737301"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="11d6c-102">IMetaDataEmit::SetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="11d6c-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="11d6c-103">Establece la información para el parámetro de campo, el valor devuelto del método o el método al que hace referencia el token especificado de cálculo de referencias de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="11d6c-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d6c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11d6c-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11d6c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11d6c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="11d6c-106">[in] El token para el elemento de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="11d6c-106">[in] The token for target data item.</span></span> <span data-ttu-id="11d6c-107">Puede ser un `mdFieldDef` o un `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="11d6c-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="11d6c-108">[in] La firma para el tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="11d6c-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="11d6c-109">[in] El recuento de bytes en `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="11d6c-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11d6c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11d6c-110">Requirements</span></span>  
 <span data-ttu-id="11d6c-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11d6c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11d6c-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="11d6c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11d6c-113">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11d6c-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11d6c-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11d6c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d6c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="11d6c-115">See also</span></span>
- [<span data-ttu-id="11d6c-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11d6c-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="11d6c-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11d6c-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
