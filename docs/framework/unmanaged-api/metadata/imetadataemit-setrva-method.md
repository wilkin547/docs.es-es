---
title: IMetaDataEmit::SetRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1a9df30ae11b13c052c75b05b0850d9f4754620
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470099"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="8561c-102">IMetaDataEmit::SetRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="8561c-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="8561c-103">Establece la dirección virtual relativa del método especificado.</span><span class="sxs-lookup"><span data-stu-id="8561c-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8561c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8561c-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8561c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8561c-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="8561c-106">[in] El token para el método de destino o la implementación del método.</span><span class="sxs-lookup"><span data-stu-id="8561c-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="8561c-107">[in] La dirección del área del código o datos.</span><span class="sxs-lookup"><span data-stu-id="8561c-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8561c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8561c-108">Requirements</span></span>  
 <span data-ttu-id="8561c-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8561c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8561c-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="8561c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8561c-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8561c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8561c-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8561c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8561c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8561c-113">See also</span></span>
- [<span data-ttu-id="8561c-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8561c-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8561c-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8561c-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
