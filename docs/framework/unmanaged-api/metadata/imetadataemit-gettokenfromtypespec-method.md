---
description: 'Más información sobre: IMetaDataEmit:: GetTokenFromTypeSpec ((método)'
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
ms.openlocfilehash: 09f7133af9b9d912b03cdc1c93744ee260c69169
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728241"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="15cf5-103">IMetaDataEmit::GetTokenFromTypeSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="15cf5-103">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>

<span data-ttu-id="15cf5-104">Obtiene un símbolo (token) de metadatos para el tipo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="15cf5-104">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15cf5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15cf5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15cf5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15cf5-106">Parameters</span></span>  

 `pvSig`  
 <span data-ttu-id="15cf5-107">de Firma que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="15cf5-107">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="15cf5-108">de Recuento de bytes de `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="15cf5-108">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="15cf5-109">enuncia El `mdTypeSpec` token asignado.</span><span class="sxs-lookup"><span data-stu-id="15cf5-109">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15cf5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15cf5-110">Requirements</span></span>  

 <span data-ttu-id="15cf5-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15cf5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15cf5-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="15cf5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15cf5-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15cf5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15cf5-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15cf5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15cf5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="15cf5-115">See also</span></span>

- [<span data-ttu-id="15cf5-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15cf5-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="15cf5-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15cf5-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
