---
description: 'Más información sobre: IMetaDataEmit:: Setparamprops ((método)'
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
ms.openlocfilehash: 35e839b05b3671c6c09f315ac636971c386e766e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772032"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="91e8b-103">IMetaDataEmit::SetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="91e8b-103">IMetaDataEmit::SetParamProps Method</span></span>

<span data-ttu-id="91e8b-104">Establece o cambia las características de un parámetro de método que se definió mediante una llamada anterior a [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="91e8b-104">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91e8b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91e8b-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="91e8b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91e8b-106">Parameters</span></span>  

 `pd`  
 <span data-ttu-id="91e8b-107">de El token para el parámetro de destino.</span><span class="sxs-lookup"><span data-stu-id="91e8b-107">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="91e8b-108">de Nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="91e8b-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="91e8b-109">de Marcas para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="91e8b-109">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="91e8b-110">de ELEMENT_TYPE_ \* para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="91e8b-110">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="91e8b-111">de Valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="91e8b-111">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="91e8b-112">de El tamaño en caracteres (Unicode) de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="91e8b-112">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91e8b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91e8b-113">Requirements</span></span>  

 <span data-ttu-id="91e8b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91e8b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91e8b-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="91e8b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91e8b-116">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91e8b-116">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91e8b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91e8b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e8b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="91e8b-118">See also</span></span>

- [<span data-ttu-id="91e8b-119">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91e8b-119">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="91e8b-120">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91e8b-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
