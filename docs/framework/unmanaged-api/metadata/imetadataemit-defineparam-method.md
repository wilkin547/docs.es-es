---
title: "IMetaDataEmit::DefineParam (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4bf36edfad504f2858a45d5e34891042d8850bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="2d869-102">IMetaDataEmit::DefineParam (Método)</span><span class="sxs-lookup"><span data-stu-id="2d869-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="2d869-103">Crea una definición de parámetro con la firma especificada para el método al que hace referencia el token especificado y obtiene un símbolo (token) para esa definición de parámetro.</span><span class="sxs-lookup"><span data-stu-id="2d869-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d869-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d869-104">Syntax</span></span>  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d869-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d869-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="2d869-106">[in] El token para el método cuyo parámetro se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="2d869-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="2d869-107">[in] El número de secuencia del parámetro.</span><span class="sxs-lookup"><span data-stu-id="2d869-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="2d869-108">[in] El nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="2d869-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2d869-109">[in] Marcadores para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="2d869-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="2d869-110">Se trata de una máscara de bits de `CorParamAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="2d869-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2d869-111">[in] `ELEMENT_TYPE_`  *\**  para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="2d869-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2d869-112">[in] El valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="2d869-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2d869-113">[in] El tamaño, en caracteres Unicode, de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="2d869-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="2d869-114">[out] El `mdParamDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="2d869-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d869-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d869-115">Remarks</span></span>  
 <span data-ttu-id="2d869-116">La secuencia de valores de `ulParamSeq` empiezan por 1 para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="2d869-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="2d869-117">Un valor devuelto tiene un número de secuencia de 0.</span><span class="sxs-lookup"><span data-stu-id="2d869-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d869-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d869-118">Requirements</span></span>  
 <span data-ttu-id="2d869-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d869-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d869-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2d869-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2d869-121">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d869-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d869-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d869-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d869-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d869-123">See Also</span></span>  
 [<span data-ttu-id="2d869-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d869-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="2d869-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d869-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
