---
title: "IMetaDataEmit::SetRVA (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a9ea1fe9afdb16f956ff8a0019a9bb607aa87f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="a6dd6-102">IMetaDataEmit::SetRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="a6dd6-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="a6dd6-103">Establece la dirección virtual relativa del método especificado.</span><span class="sxs-lookup"><span data-stu-id="a6dd6-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6dd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6dd6-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6dd6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6dd6-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="a6dd6-106">[in] El token para el método de destino o la implementación del método.</span><span class="sxs-lookup"><span data-stu-id="a6dd6-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="a6dd6-107">[in] La dirección del área de código o datos.</span><span class="sxs-lookup"><span data-stu-id="a6dd6-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6dd6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6dd6-108">Requirements</span></span>  
 <span data-ttu-id="a6dd6-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6dd6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6dd6-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a6dd6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6dd6-111">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6dd6-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6dd6-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6dd6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6dd6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6dd6-113">See Also</span></span>  
 [<span data-ttu-id="a6dd6-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6dd6-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a6dd6-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6dd6-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
