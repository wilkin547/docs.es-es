---
title: IMetaDataEmit::SetFieldProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: 0f98fb64b43822c437c39df2f3c51a222ef386b9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730401"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="7cb39-102">IMetaDataEmit::SetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7cb39-102">IMetaDataEmit::SetFieldProps Method</span></span>

<span data-ttu-id="7cb39-103">Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="7cb39-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cb39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cb39-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cb39-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7cb39-105">Parameters</span></span>  

 `fd`  
 <span data-ttu-id="7cb39-106">de El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="7cb39-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="7cb39-107">de Atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="7cb39-107">[in] Field attributes.</span></span> <span data-ttu-id="7cb39-108">Se trata de una máscara de máscara de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="7cb39-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="7cb39-109">de `ELEMENT_TYPE_` *\** Para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="7cb39-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="7cb39-110">Este es un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="7cb39-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="7cb39-111">Si no se define una constante, establezca este valor en `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="7cb39-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="7cb39-112">de Valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="7cb39-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="7cb39-113">de Tamaño, en caracteres Unicode, de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="7cb39-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cb39-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cb39-114">Requirements</span></span>  

 <span data-ttu-id="7cb39-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cb39-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cb39-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7cb39-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cb39-117">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7cb39-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7cb39-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cb39-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb39-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7cb39-119">See also</span></span>

- [<span data-ttu-id="7cb39-120">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cb39-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7cb39-121">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7cb39-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
