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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ccafea78aa2497c52442a10ad1af1c05771df7e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737107"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="f1ae5-102">IMetaDataEmit::SetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="f1ae5-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="f1ae5-103">Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ae5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1ae5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1ae5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1ae5-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="f1ae5-106">[in] El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="f1ae5-107">[in] Atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-107">[in] Field attributes.</span></span> <span data-ttu-id="f1ae5-108">Se trata de una máscara de bits de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="f1ae5-109">[in] El `ELEMENT_TYPE_` *\** para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="f1ae5-110">Se trata de un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="f1ae5-111">Si no se está definiendo una constante, establezca este valor en `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f1ae5-112">[in] El valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="f1ae5-113">[in] El tamaño, en caracteres Unicode, de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="f1ae5-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ae5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1ae5-114">Requirements</span></span>  
 <span data-ttu-id="f1ae5-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1ae5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ae5-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1ae5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1ae5-117">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1ae5-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1ae5-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ae5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ae5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1ae5-119">See also</span></span>

- [<span data-ttu-id="f1ae5-120">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1ae5-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f1ae5-121">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1ae5-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
