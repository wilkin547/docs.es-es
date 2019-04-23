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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6969f2c1df9b5b04122ed6aef550697171123cf5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229022"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="95abb-102">IMetaDataFilter::IsTokenMarked (Método)</span><span class="sxs-lookup"><span data-stu-id="95abb-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="95abb-103">Obtiene un valor que indica si el token de metadatos especificado se ha marcado como procesado.</span><span class="sxs-lookup"><span data-stu-id="95abb-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95abb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95abb-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95abb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95abb-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="95abb-106">[in] El token para examinar una marca de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="95abb-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="95abb-107">[out] Un valor que es `true` si `tk` se ha procesado; en caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="95abb-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95abb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95abb-108">Requirements</span></span>  
 <span data-ttu-id="95abb-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95abb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95abb-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="95abb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95abb-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95abb-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95abb-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95abb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95abb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="95abb-113">See also</span></span>

- [<span data-ttu-id="95abb-114">IMetaDataFilter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="95abb-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
