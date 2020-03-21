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
ms.openlocfilehash: b921118f7c43edef3c07cbb34cbbd9119d36ce51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177547"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="a51c3-102">IMetaDataEmit::SetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="a51c3-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="a51c3-103">Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="a51c3-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a51c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a51c3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a51c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a51c3-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="a51c3-106">[en] El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="a51c3-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="a51c3-107">[en] Atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="a51c3-107">[in] Field attributes.</span></span> <span data-ttu-id="a51c3-108">Esta es una `CorFieldAttr` máscara de bits de valores.</span><span class="sxs-lookup"><span data-stu-id="a51c3-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="a51c3-109">[en] El `ELEMENT_TYPE_` *\** valor constante for.</span><span class="sxs-lookup"><span data-stu-id="a51c3-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="a51c3-110">Este es `CorElementType` un valor.</span><span class="sxs-lookup"><span data-stu-id="a51c3-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="a51c3-111">Si no se está definiendo una `ELEMENT_TYPE_END`constante, establezca este valor en .</span><span class="sxs-lookup"><span data-stu-id="a51c3-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a51c3-112">[en] El valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="a51c3-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="a51c3-113">[en] El tamaño, en caracteres Unicode, de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="a51c3-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a51c3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a51c3-114">Requirements</span></span>  
 <span data-ttu-id="a51c3-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a51c3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a51c3-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a51c3-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a51c3-117">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a51c3-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a51c3-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a51c3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51c3-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a51c3-119">See also</span></span>

- [<span data-ttu-id="a51c3-120">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a51c3-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a51c3-121">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a51c3-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
