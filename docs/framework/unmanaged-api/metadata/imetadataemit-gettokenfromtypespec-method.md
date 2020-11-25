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
ms.openlocfilehash: 3a8f369728b8464850259518981bf6690cb17a01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722044"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="100e5-102">IMetaDataEmit::GetTokenFromTypeSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="100e5-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>

<span data-ttu-id="100e5-103">Obtiene un símbolo (token) de metadatos para el tipo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="100e5-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="100e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="100e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="100e5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="100e5-105">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="100e5-106">de Firma que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="100e5-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="100e5-107">de Recuento de bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="100e5-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="100e5-108">enuncia El `mdTypeSpec` token asignado.</span><span class="sxs-lookup"><span data-stu-id="100e5-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="100e5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="100e5-109">Requirements</span></span>  

 <span data-ttu-id="100e5-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="100e5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="100e5-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="100e5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="100e5-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="100e5-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="100e5-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="100e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="100e5-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="100e5-114">See also</span></span>

- [<span data-ttu-id="100e5-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="100e5-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="100e5-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="100e5-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
