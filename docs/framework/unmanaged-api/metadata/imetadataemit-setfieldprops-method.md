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
ms.openlocfilehash: 94ba607669b4b1ca68294470cf1cc4fb27464d28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097660"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="c98e2-102">IMetaDataEmit::SetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="c98e2-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="c98e2-103">Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="c98e2-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c98e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c98e2-104">Syntax</span></span>  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c98e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c98e2-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="c98e2-106">[in] El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="c98e2-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="c98e2-107">[in] Atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="c98e2-107">[in] Field attributes.</span></span> <span data-ttu-id="c98e2-108">Se trata de una máscara de bits de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="c98e2-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="c98e2-109">[in] El `ELEMENT_TYPE_` *\** para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="c98e2-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="c98e2-110">Se trata de un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="c98e2-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="c98e2-111">Si no se está definiendo una constante, establezca este valor en `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="c98e2-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="c98e2-112">[in] El valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="c98e2-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="c98e2-113">[in] El tamaño, en caracteres Unicode, de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="c98e2-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c98e2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c98e2-114">Requirements</span></span>  
 <span data-ttu-id="c98e2-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c98e2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c98e2-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c98e2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c98e2-117">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c98e2-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c98e2-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c98e2-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c98e2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c98e2-119">See also</span></span>

- [<span data-ttu-id="c98e2-120">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c98e2-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c98e2-121">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c98e2-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
