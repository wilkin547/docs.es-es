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
ms.openlocfilehash: b0cc28807938bcfb9b2465093ff4cfb94066ee98
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675066"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="8d3d7-102">IMetaDataEmit::SetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="8d3d7-102">IMetaDataEmit::SetParamProps Method</span></span>

<span data-ttu-id="8d3d7-103">Establece o cambia las características de un parámetro de método que se definió mediante una llamada anterior a [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="8d3d7-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d3d7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8d3d7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d3d7-105">Parameters</span></span>  

 `pd`  
 <span data-ttu-id="8d3d7-106">de El token para el parámetro de destino.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="8d3d7-107">de Nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="8d3d7-108">de Marcas para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="8d3d7-109">de ELEMENT_TYPE_ \* para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8d3d7-110">de Valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="8d3d7-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="8d3d7-111">de El tamaño en caracteres (Unicode) de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="8d3d7-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d3d7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d3d7-112">Requirements</span></span>  

 <span data-ttu-id="8d3d7-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d3d7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d3d7-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8d3d7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d3d7-115">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d3d7-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d3d7-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d3d7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3d7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d3d7-117">See also</span></span>

- [<span data-ttu-id="8d3d7-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d3d7-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8d3d7-119">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d3d7-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
