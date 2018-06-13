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
ms.openlocfilehash: 6b699539df52bda9206191dd89c0f95de69140a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443891"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="37dfc-102">IMetaDataEmit::SetCustomAttributeValue (Método)</span><span class="sxs-lookup"><span data-stu-id="37dfc-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="37dfc-103">Establece o actualiza el valor de un atributo personalizado definido por una llamada anterior a [IMetaDataEmit:: DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="37dfc-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37dfc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37dfc-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37dfc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37dfc-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="37dfc-106">[in] El token del atributo personalizado de destino.</span><span class="sxs-lookup"><span data-stu-id="37dfc-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="37dfc-107">[in] Un puntero a la matriz que contiene el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="37dfc-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="37dfc-108">[in] El tamaño, en bytes, del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="37dfc-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37dfc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37dfc-109">Requirements</span></span>  
 <span data-ttu-id="37dfc-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37dfc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37dfc-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37dfc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37dfc-112">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37dfc-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37dfc-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37dfc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37dfc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="37dfc-114">See Also</span></span>  
 [<span data-ttu-id="37dfc-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="37dfc-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="37dfc-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="37dfc-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
