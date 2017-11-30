---
title: "IMetaDataEmit::SetCustomAttributeValue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetCustomAttributeValue
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 30538b0f6f6aa196edf8373f5f4e6f09ba903223
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="9ded4-102">IMetaDataEmit::SetCustomAttributeValue (Método)</span><span class="sxs-lookup"><span data-stu-id="9ded4-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="9ded4-103">Establece o actualiza el valor de un atributo personalizado definido por una llamada anterior a [IMetaDataEmit:: DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="9ded4-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ded4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ded4-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ded4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ded4-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="9ded4-106">[in] El token del atributo personalizado de destino.</span><span class="sxs-lookup"><span data-stu-id="9ded4-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="9ded4-107">[in] Un puntero a la matriz que contiene el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="9ded4-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="9ded4-108">[in] El tamaño, en bytes, del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="9ded4-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ded4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ded4-109">Requirements</span></span>  
 <span data-ttu-id="9ded4-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ded4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ded4-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9ded4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ded4-112">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ded4-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ded4-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ded4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ded4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ded4-114">See Also</span></span>  
 [<span data-ttu-id="9ded4-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ded4-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9ded4-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ded4-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
