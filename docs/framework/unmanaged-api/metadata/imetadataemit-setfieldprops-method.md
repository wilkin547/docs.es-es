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
ms.openlocfilehash: 220556ec130c7bff7c413405820c4fee0582b051
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008019"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="e6f01-102">IMetaDataEmit::SetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e6f01-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="e6f01-103">Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="e6f01-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6f01-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6f01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6f01-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="e6f01-106">de El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="e6f01-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="e6f01-107">de Atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="e6f01-107">[in] Field attributes.</span></span> <span data-ttu-id="e6f01-108">Se trata de una máscara de máscara de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="e6f01-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="e6f01-109">de `ELEMENT_TYPE_` *\** Para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="e6f01-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="e6f01-110">Este es un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="e6f01-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="e6f01-111">Si no se define una constante, establezca este valor en `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="e6f01-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="e6f01-112">de Valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="e6f01-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="e6f01-113">de Tamaño, en caracteres Unicode, de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="e6f01-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f01-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6f01-114">Requirements</span></span>  
 <span data-ttu-id="e6f01-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6f01-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f01-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e6f01-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6f01-117">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e6f01-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6f01-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f01-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f01-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6f01-119">See also</span></span>

- [<span data-ttu-id="e6f01-120">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6f01-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e6f01-121">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6f01-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
