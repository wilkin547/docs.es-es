---
title: IMetaDataEmit::GetTokenFromTypeSpec (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 1cd09fe785bb37c892417ddbf1efaaaa90e121bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009241"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="98c8f-102">IMetaDataEmit::GetTokenFromTypeSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="98c8f-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="98c8f-103">Obtiene un símbolo (token) de metadatos para el tipo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="98c8f-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98c8f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98c8f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98c8f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98c8f-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="98c8f-106">de Firma que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="98c8f-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="98c8f-107">de Recuento de bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="98c8f-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="98c8f-108">enuncia El `mdTypeSpec` token asignado.</span><span class="sxs-lookup"><span data-stu-id="98c8f-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98c8f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98c8f-109">Requirements</span></span>  
 <span data-ttu-id="98c8f-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98c8f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98c8f-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="98c8f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98c8f-112">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="98c8f-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98c8f-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98c8f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c8f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98c8f-114">See also</span></span>

- [<span data-ttu-id="98c8f-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98c8f-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="98c8f-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98c8f-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
