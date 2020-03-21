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
ms.openlocfilehash: 47377e892aaf2bdd96a297630c47fe52215b0564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177383"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="dedfb-102">IMetaDataFilter::IsTokenMarked (Método)</span><span class="sxs-lookup"><span data-stu-id="dedfb-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="dedfb-103">Obtiene un valor que indica si el token de metadatos especificado se ha marcado como procesado.</span><span class="sxs-lookup"><span data-stu-id="dedfb-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dedfb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dedfb-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dedfb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dedfb-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="dedfb-106">[en] El token que se examinará para una marca de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="dedfb-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="dedfb-107">[fuera] Un valor `true` que `tk` es si se ha procesado; de `false`lo contrario .</span><span class="sxs-lookup"><span data-stu-id="dedfb-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dedfb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dedfb-108">Requirements</span></span>  
 <span data-ttu-id="dedfb-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dedfb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dedfb-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dedfb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dedfb-111">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dedfb-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dedfb-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dedfb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dedfb-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dedfb-113">See also</span></span>

- [<span data-ttu-id="dedfb-114">IMetaDataFilter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dedfb-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
