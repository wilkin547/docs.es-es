---
description: 'Más información sobre: IMetaDataFilter:: Istokenmarked ((método)'
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
ms.openlocfilehash: dddb0aa9040a2f5ef3ec972bb37a9e8778ddffe8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677794"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="109a8-103">IMetaDataFilter::IsTokenMarked (Método)</span><span class="sxs-lookup"><span data-stu-id="109a8-103">IMetaDataFilter::IsTokenMarked Method</span></span>

<span data-ttu-id="109a8-104">Obtiene un valor que indica si el token de metadatos especificado se ha marcado como procesado.</span><span class="sxs-lookup"><span data-stu-id="109a8-104">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="109a8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="109a8-105">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="109a8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="109a8-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="109a8-107">de Token que se va a examinar para una marca de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="109a8-107">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="109a8-108">enuncia Valor que es si se ha `true` `tk` procesado; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="109a8-108">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="109a8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="109a8-109">Requirements</span></span>  

 <span data-ttu-id="109a8-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="109a8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="109a8-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="109a8-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="109a8-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="109a8-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="109a8-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="109a8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="109a8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="109a8-114">See also</span></span>

- [<span data-ttu-id="109a8-115">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="109a8-115">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
