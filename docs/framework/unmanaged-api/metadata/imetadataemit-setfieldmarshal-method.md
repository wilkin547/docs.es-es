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
ms.openlocfilehash: d0066c6590a9e0cf278e036111c2739f7cfaf679
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003911"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="62468-102">IMetaDataEmit::SetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="62468-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="62468-103">Establece la información de serialización de PInvoke para el campo, el valor devuelto por el método o el parámetro de método al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="62468-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62468-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62468-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62468-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62468-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="62468-106">de El token para el elemento de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="62468-106">[in] The token for target data item.</span></span> <span data-ttu-id="62468-107">Este es un `mdFieldDef` `mdParamDef` token o.</span><span class="sxs-lookup"><span data-stu-id="62468-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="62468-108">de Firma para el tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="62468-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="62468-109">de Recuento de bytes de `pvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="62468-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62468-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62468-110">Requirements</span></span>  
 <span data-ttu-id="62468-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62468-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62468-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="62468-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62468-113">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62468-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62468-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62468-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62468-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62468-115">See also</span></span>

- [<span data-ttu-id="62468-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62468-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="62468-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62468-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
