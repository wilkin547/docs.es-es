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
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007824"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="1b40d-102">IMetaDataEmit::SetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="1b40d-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="1b40d-103">Establece o cambia las características de un parámetro de método que se definió mediante una llamada anterior a [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="1b40d-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b40d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b40d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1b40d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b40d-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="1b40d-106">de El token para el parámetro de destino.</span><span class="sxs-lookup"><span data-stu-id="1b40d-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="1b40d-107">de Nombre del parámetro en Unicode.</span><span class="sxs-lookup"><span data-stu-id="1b40d-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="1b40d-108">de Marcas para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="1b40d-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="1b40d-109">de ELEMENT_TYPE_ \* para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="1b40d-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="1b40d-110">de Valor constante para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="1b40d-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="1b40d-111">de El tamaño en caracteres (Unicode) de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="1b40d-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b40d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b40d-112">Requirements</span></span>  
 <span data-ttu-id="1b40d-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b40d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b40d-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1b40d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b40d-115">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1b40d-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b40d-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b40d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b40d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b40d-117">See also</span></span>

- [<span data-ttu-id="1b40d-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b40d-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1b40d-119">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b40d-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
