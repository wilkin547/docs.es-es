---
title: IMetaDataEmit::DefineParam (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d64a1ef21cd4fa4224609c7cd415c1611313769
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777552"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="d5a50-102">IMetaDataEmit::DefineParam (Método)</span><span class="sxs-lookup"><span data-stu-id="d5a50-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="d5a50-103">Crea una definición de parámetro con la firma especificada para el método al que hace referencia el token especificado y obtiene un token para esa definición de parámetro.</span><span class="sxs-lookup"><span data-stu-id="d5a50-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5a50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5a50-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="d5a50-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5a50-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="d5a50-106">[in] El token para el método cuyo parámetro se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="d5a50-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="d5a50-107">[in] El número de secuencia del parámetro.</span><span class="sxs-lookup"><span data-stu-id="d5a50-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="d5a50-108">[in] El nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="d5a50-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="d5a50-109">[in] Marcas para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="d5a50-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="d5a50-110">Se trata de una máscara de bits de `CorParamAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="d5a50-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="d5a50-111">[in] `ELEMENT_TYPE_` *\** para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="d5a50-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="d5a50-112">[in] El valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="d5a50-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="d5a50-113">[in] El tamaño, en caracteres Unicode, de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="d5a50-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="d5a50-114">[out] El `mdParamDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="d5a50-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5a50-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5a50-115">Remarks</span></span>  
 <span data-ttu-id="d5a50-116">Los valores de secuencia en `ulParamSeq` comienzan por 1 para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="d5a50-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="d5a50-117">Un valor devuelto tiene un número de secuencia de 0.</span><span class="sxs-lookup"><span data-stu-id="d5a50-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5a50-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5a50-118">Requirements</span></span>  
 <span data-ttu-id="d5a50-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5a50-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5a50-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5a50-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5a50-121">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5a50-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5a50-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5a50-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a50-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5a50-123">See also</span></span>

- [<span data-ttu-id="d5a50-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5a50-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d5a50-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5a50-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
