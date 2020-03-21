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
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177693"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="950ee-102">IMetaDataEmit::DefineParam (Método)</span><span class="sxs-lookup"><span data-stu-id="950ee-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="950ee-103">Crea una definición de parámetro con la firma especificada para el método al que hace referencia el token especificado y obtiene un token para esa definición de parámetro.</span><span class="sxs-lookup"><span data-stu-id="950ee-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="950ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="950ee-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="950ee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="950ee-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="950ee-106">[en] El token para el método cuyo parámetro se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="950ee-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="950ee-107">[en] El número de secuencia de parámetros.</span><span class="sxs-lookup"><span data-stu-id="950ee-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="950ee-108">[en] El nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="950ee-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="950ee-109">[en] Indicadores para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="950ee-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="950ee-110">Esta es una `CorParamAttr` máscara de bits de valores.</span><span class="sxs-lookup"><span data-stu-id="950ee-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="950ee-111">[en] `ELEMENT_TYPE_` para el valor *\** constante.</span><span class="sxs-lookup"><span data-stu-id="950ee-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="950ee-112">[en] El valor constante del parámetro.</span><span class="sxs-lookup"><span data-stu-id="950ee-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="950ee-113">[en] El tamaño, en caracteres Unicode, de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="950ee-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="950ee-114">[fuera] El `mdParamDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="950ee-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="950ee-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="950ee-115">Remarks</span></span>  
 <span data-ttu-id="950ee-116">Los valores `ulParamSeq` de secuencia comienzan con 1 para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="950ee-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="950ee-117">Un valor devuelto tiene un número de secuencia de 0.</span><span class="sxs-lookup"><span data-stu-id="950ee-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="950ee-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="950ee-118">Requirements</span></span>  
 <span data-ttu-id="950ee-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="950ee-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="950ee-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="950ee-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="950ee-121">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="950ee-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="950ee-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="950ee-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="950ee-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="950ee-123">See also</span></span>

- [<span data-ttu-id="950ee-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="950ee-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="950ee-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="950ee-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
