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
ms.openlocfilehash: a58e03875ec021b41479085fa9e27a4321ae965e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004379"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="5c48a-102">IMetaDataEmit::DefineParam (Método)</span><span class="sxs-lookup"><span data-stu-id="5c48a-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="5c48a-103">Crea una definición de parámetro con la firma especificada para el método al que hace referencia el token especificado y obtiene un token para esa definición de parámetro.</span><span class="sxs-lookup"><span data-stu-id="5c48a-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c48a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c48a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5c48a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c48a-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="5c48a-106">de El token para el método cuyo parámetro se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="5c48a-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="5c48a-107">de El número de secuencia del parámetro.</span><span class="sxs-lookup"><span data-stu-id="5c48a-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="5c48a-108">de Nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="5c48a-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="5c48a-109">de Marcas para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="5c48a-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="5c48a-110">Se trata de una máscara de máscara de `CorParamAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="5c48a-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="5c48a-111">[in] `ELEMENT_TYPE_` *\** para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="5c48a-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5c48a-112">de Valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="5c48a-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="5c48a-113">de Tamaño, en caracteres Unicode, de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="5c48a-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="5c48a-114">enuncia El `mdParamDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="5c48a-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c48a-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c48a-115">Remarks</span></span>  
 <span data-ttu-id="5c48a-116">Los valores de secuencia de `ulParamSeq` comienzan por 1 para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="5c48a-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="5c48a-117">Un valor devuelto tiene un número de secuencia de 0.</span><span class="sxs-lookup"><span data-stu-id="5c48a-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c48a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c48a-118">Requirements</span></span>  
 <span data-ttu-id="5c48a-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c48a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c48a-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c48a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c48a-121">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c48a-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c48a-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c48a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c48a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c48a-123">See also</span></span>

- [<span data-ttu-id="5c48a-124">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c48a-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5c48a-125">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c48a-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
