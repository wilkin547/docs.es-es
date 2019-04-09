---
title: IMetaDataEmit::SetCustomAttributeValue (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f9e684b90dcc7f0ff83962361486caf7e991568
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096347"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="7ef93-102">IMetaDataEmit::SetCustomAttributeValue (Método)</span><span class="sxs-lookup"><span data-stu-id="7ef93-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="7ef93-103">Establece o actualiza el valor de un atributo personalizado definido por una llamada anterior a [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="7ef93-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ef93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ef93-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ef93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ef93-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="7ef93-106">[in] El token del atributo personalizado de destino.</span><span class="sxs-lookup"><span data-stu-id="7ef93-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="7ef93-107">[in] Un puntero a la matriz que contiene el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="7ef93-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="7ef93-108">[in] El tamaño, en bytes, del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="7ef93-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ef93-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ef93-109">Requirements</span></span>  
 <span data-ttu-id="7ef93-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ef93-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ef93-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ef93-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ef93-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ef93-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7ef93-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7ef93-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7ef93-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ef93-114">See also</span></span>

- [<span data-ttu-id="7ef93-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ef93-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7ef93-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ef93-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
