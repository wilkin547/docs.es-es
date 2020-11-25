---
title: IMetaDataFilter::MarkToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
ms.openlocfilehash: c942838fb62bf86c4054761f4e7f2ef0518b3d89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701818"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="b7606-102">IMetaDataFilter::MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="b7606-102">IMetaDataFilter::MarkToken Method</span></span>

<span data-ttu-id="b7606-103">Establece un valor que indica que se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="b7606-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7606-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7606-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7606-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7606-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="b7606-106">de Token que se va a marcar como procesado.</span><span class="sxs-lookup"><span data-stu-id="b7606-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7606-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7606-107">Requirements</span></span>  

 <span data-ttu-id="b7606-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7606-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7606-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b7606-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7606-110">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7606-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7606-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7606-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7606-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7606-112">See also</span></span>

- [<span data-ttu-id="b7606-113">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7606-113">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
