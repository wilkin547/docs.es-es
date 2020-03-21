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
ms.openlocfilehash: 1037cd4210605192870d43d88979b89af6536380
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175660"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="e160b-102">IMetaDataEmit::SetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="e160b-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="e160b-103">Establece la información de cálculo de referencias pInvoke para el campo, el valor devuelto por el método o el parámetro de método al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="e160b-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e160b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e160b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e160b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e160b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e160b-106">[en] El token para el elemento de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="e160b-106">[in] The token for target data item.</span></span> <span data-ttu-id="e160b-107">Esto es `mdFieldDef` un `mdParamDef` token o un token.</span><span class="sxs-lookup"><span data-stu-id="e160b-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="e160b-108">[en] La firma para el tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="e160b-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="e160b-109">[en] El recuento de `pvNativeType`bytes en .</span><span class="sxs-lookup"><span data-stu-id="e160b-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e160b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e160b-110">Requirements</span></span>  
 <span data-ttu-id="e160b-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e160b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e160b-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e160b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e160b-113">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e160b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e160b-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e160b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e160b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e160b-115">See also</span></span>

- [<span data-ttu-id="e160b-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e160b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e160b-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e160b-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
