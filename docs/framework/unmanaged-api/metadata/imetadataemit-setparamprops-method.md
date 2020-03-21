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
ms.openlocfilehash: 13220dcfdd260688494d5aebc50f94abf8a82215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177507"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="766fc-102">IMetaDataEmit::SetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="766fc-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="766fc-103">Establece o cambia las características de un parámetro de método definido por una llamada anterior a [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="766fc-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="766fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="766fc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="766fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="766fc-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="766fc-106">[en] El token para el parámetro de destino.</span><span class="sxs-lookup"><span data-stu-id="766fc-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="766fc-107">[en] El nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="766fc-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="766fc-108">[en] Las marcas del parámetro.</span><span class="sxs-lookup"><span data-stu-id="766fc-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="766fc-109">[en] El ELEMENT_TYPE_\* para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="766fc-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="766fc-110">[en] El valor constante del parámetro.</span><span class="sxs-lookup"><span data-stu-id="766fc-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="766fc-111">[en] El tamaño en caracteres `pValue`(Unicode) de .</span><span class="sxs-lookup"><span data-stu-id="766fc-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="766fc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="766fc-112">Requirements</span></span>  
 <span data-ttu-id="766fc-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="766fc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="766fc-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="766fc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="766fc-115">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="766fc-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="766fc-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="766fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="766fc-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="766fc-117">See also</span></span>

- [<span data-ttu-id="766fc-118">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="766fc-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="766fc-119">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="766fc-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
