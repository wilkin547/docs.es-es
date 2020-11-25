---
title: IMetaDataFilter::IsTokenMarked (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
ms.openlocfilehash: ce7292003872805c9390ce3d9c59b39497a83ed1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701840"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="39116-102">IMetaDataFilter::IsTokenMarked (Método)</span><span class="sxs-lookup"><span data-stu-id="39116-102">IMetaDataFilter::IsTokenMarked Method</span></span>

<span data-ttu-id="39116-103">Obtiene un valor que indica si el token de metadatos especificado se ha marcado como procesado.</span><span class="sxs-lookup"><span data-stu-id="39116-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39116-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39116-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39116-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39116-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="39116-106">de Token que se va a examinar para una marca de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="39116-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="39116-107">enuncia Valor que es si se ha `true` `tk` procesado; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="39116-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39116-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39116-108">Requirements</span></span>  

 <span data-ttu-id="39116-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39116-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39116-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="39116-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39116-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39116-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39116-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39116-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39116-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39116-113">See also</span></span>

- [<span data-ttu-id="39116-114">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39116-114">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
