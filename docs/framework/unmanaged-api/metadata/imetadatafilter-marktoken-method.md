---
description: 'Más información sobre: IMetaDataFilter:: MarkToken ((método)'
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
ms.openlocfilehash: 97191533ae7d2bdc951521f1929a4c001c521b9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677800"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="1ae54-103">IMetaDataFilter::MarkToken (Método)</span><span class="sxs-lookup"><span data-stu-id="1ae54-103">IMetaDataFilter::MarkToken Method</span></span>

<span data-ttu-id="1ae54-104">Establece un valor que indica que se ha procesado el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="1ae54-104">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae54-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ae54-105">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ae54-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ae54-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="1ae54-107">de Token que se va a marcar como procesado.</span><span class="sxs-lookup"><span data-stu-id="1ae54-107">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ae54-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ae54-108">Requirements</span></span>  

 <span data-ttu-id="1ae54-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ae54-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ae54-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1ae54-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ae54-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ae54-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ae54-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ae54-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae54-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ae54-113">See also</span></span>

- [<span data-ttu-id="1ae54-114">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ae54-114">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
