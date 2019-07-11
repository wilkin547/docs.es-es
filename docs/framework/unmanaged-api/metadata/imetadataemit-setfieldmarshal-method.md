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
ms.openlocfilehash: a55a8575a3f8ae04bcc4a148b588cd2361f81cf6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751499"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="ace93-102">IMetaDataEmit::SetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="ace93-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="ace93-103">Establece la información para el parámetro de campo, el valor devuelto del método o el método al que hace referencia el token especificado de cálculo de referencias de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ace93-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ace93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ace93-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ace93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ace93-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ace93-106">[in] El token para el elemento de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="ace93-106">[in] The token for target data item.</span></span> <span data-ttu-id="ace93-107">Puede ser un `mdFieldDef` o un `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="ace93-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="ace93-108">[in] La firma para el tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="ace93-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="ace93-109">[in] El recuento de bytes en `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="ace93-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ace93-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ace93-110">Requirements</span></span>  
 <span data-ttu-id="ace93-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ace93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ace93-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ace93-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ace93-113">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ace93-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ace93-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ace93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace93-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ace93-115">See also</span></span>

- [<span data-ttu-id="ace93-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ace93-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ace93-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ace93-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
