---
title: "IMetaDataEmit::SetParamProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ac76a9af6839ea08169c8b9c143fa96066e954ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="5febd-102">IMetaDataEmit::SetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5febd-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="5febd-103">Establece o cambia las características de un parámetro de método que se definió mediante una llamada anterior a [IMetaDataEmit:: DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="5febd-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5febd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5febd-104">Syntax</span></span>  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5febd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5febd-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="5febd-106">[in] El token para el parámetro de destino.</span><span class="sxs-lookup"><span data-stu-id="5febd-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="5febd-107">[in] El nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="5febd-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="5febd-108">[in] Las marcas para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="5febd-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="5febd-109">[in] El ELEMENT_TYPE_ * para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="5febd-109">[in] The ELEMENT_TYPE_* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5febd-110">[in] El valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="5febd-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="5febd-111">[in] El tamaño en caracteres (Unicode) de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="5febd-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5febd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5febd-112">Requirements</span></span>  
 <span data-ttu-id="5febd-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5febd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5febd-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5febd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5febd-115">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5febd-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5febd-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5febd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5febd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5febd-117">See Also</span></span>  
 [<span data-ttu-id="5febd-118">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5febd-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5febd-119">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5febd-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
