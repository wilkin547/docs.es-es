---
title: IMetaDataEmit::SetParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2885d89883ab6312c2ad9d3feac405eef2fbede
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693696"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="b352a-102">IMetaDataEmit::SetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b352a-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="b352a-103">Establece o cambia las características de un parámetro de método que se ha definido por una llamada anterior a [DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="b352a-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b352a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b352a-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="b352a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b352a-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="b352a-106">[in] El token para el parámetro de destino.</span><span class="sxs-lookup"><span data-stu-id="b352a-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="b352a-107">[in] El nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="b352a-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="b352a-108">[in] Marcas para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b352a-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="b352a-109">[in] El ELEMENT_TYPE_ \* para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="b352a-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="b352a-110">[in] El valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b352a-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="b352a-111">[in] El tamaño en caracteres (Unicode) de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="b352a-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b352a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b352a-112">Requirements</span></span>  
 <span data-ttu-id="b352a-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b352a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b352a-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b352a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b352a-115">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b352a-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b352a-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b352a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b352a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b352a-117">See also</span></span>
- [<span data-ttu-id="b352a-118">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b352a-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b352a-119">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b352a-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
