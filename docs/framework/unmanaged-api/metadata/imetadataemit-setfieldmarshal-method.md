---
description: 'Más información sobre: IMetaDataEmit:: Setfieldmarshal ((método)'
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
ms.openlocfilehash: 4694487479b0249e875abfd9ecd963a5dc404d46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658053"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="7e020-103">IMetaDataEmit::SetFieldMarshal (Método)</span><span class="sxs-lookup"><span data-stu-id="7e020-103">IMetaDataEmit::SetFieldMarshal Method</span></span>

<span data-ttu-id="7e020-104">Establece la información de serialización de PInvoke para el campo, el valor devuelto por el método o el parámetro de método al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="7e020-104">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e020-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e020-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e020-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e020-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="7e020-107">de El token para el elemento de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="7e020-107">[in] The token for target data item.</span></span> <span data-ttu-id="7e020-108">Este es un `mdFieldDef` `mdParamDef` token o.</span><span class="sxs-lookup"><span data-stu-id="7e020-108">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="7e020-109">de Firma para el tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="7e020-109">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="7e020-110">de Recuento de bytes de `pvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="7e020-110">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e020-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e020-111">Requirements</span></span>  

 <span data-ttu-id="7e020-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e020-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e020-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7e020-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e020-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e020-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e020-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e020-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e020-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e020-116">See also</span></span>

- [<span data-ttu-id="7e020-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e020-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7e020-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e020-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
