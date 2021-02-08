---
description: 'Más información acerca de: IMetaDataEmit::D método efineParam'
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
ms.openlocfilehash: 300de3183b329773a8e6813d6b92c6d049d63195
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784098"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="1a268-103">IMetaDataEmit::DefineParam (Método)</span><span class="sxs-lookup"><span data-stu-id="1a268-103">IMetaDataEmit::DefineParam Method</span></span>

<span data-ttu-id="1a268-104">Crea una definición de parámetro con la firma especificada para el método al que hace referencia el token especificado y obtiene un token para esa definición de parámetro.</span><span class="sxs-lookup"><span data-stu-id="1a268-104">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a268-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a268-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1a268-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a268-106">Parameters</span></span>  

 `md`  
 <span data-ttu-id="1a268-107">de El token para el método cuyo parámetro se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="1a268-107">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="1a268-108">de El número de secuencia del parámetro.</span><span class="sxs-lookup"><span data-stu-id="1a268-108">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="1a268-109">de Nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="1a268-109">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="1a268-110">de Marcas para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="1a268-110">[in] Flags for the parameter.</span></span> <span data-ttu-id="1a268-111">Se trata de una máscara de máscara de `CorParamAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="1a268-111">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="1a268-112">[in] `ELEMENT_TYPE_` *\** para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="1a268-112">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="1a268-113">de Valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="1a268-113">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="1a268-114">de Tamaño, en caracteres Unicode, de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="1a268-114">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="1a268-115">enuncia El `mdParamDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="1a268-115">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a268-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1a268-116">Remarks</span></span>  

 <span data-ttu-id="1a268-117">Los valores de secuencia de `ulParamSeq` comienzan por 1 para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="1a268-117">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="1a268-118">Un valor devuelto tiene un número de secuencia de 0.</span><span class="sxs-lookup"><span data-stu-id="1a268-118">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a268-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a268-119">Requirements</span></span>  

 <span data-ttu-id="1a268-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a268-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a268-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1a268-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a268-122">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a268-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a268-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a268-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a268-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a268-124">See also</span></span>

- [<span data-ttu-id="1a268-125">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a268-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1a268-126">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a268-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
