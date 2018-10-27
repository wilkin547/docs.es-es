---
title: IMetaDataEmit::DefineField (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b54ceb099df15855b6b30b8c28d7d8917a9c71eb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184954"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="e99bf-102">IMetaDataEmit::DefineField (Método)</span><span class="sxs-lookup"><span data-stu-id="e99bf-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="e99bf-103">Crea una definición para un campo con la firma de metadatos especificados y obtiene un token para esa definición de campo.</span><span class="sxs-lookup"><span data-stu-id="e99bf-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e99bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e99bf-104">Syntax</span></span>  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e99bf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e99bf-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e99bf-106">[in] El `mdTypeDef` token para la clase o interfaz envolvente.</span><span class="sxs-lookup"><span data-stu-id="e99bf-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="e99bf-107">[in] El nombre del campo en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="e99bf-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="e99bf-108">[in] Los atributos del campo.</span><span class="sxs-lookup"><span data-stu-id="e99bf-108">[in] The field attributes.</span></span> <span data-ttu-id="e99bf-109">Se trata de una máscara de bits de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="e99bf-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e99bf-110">[in] La firma del campo como un BLOB.</span><span class="sxs-lookup"><span data-stu-id="e99bf-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e99bf-111">[in] El recuento de bytes en `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="e99bf-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="e99bf-112">[in] El `ELEMENT_TYPE_` *\** para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="e99bf-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="e99bf-113">Se trata de un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="e99bf-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="e99bf-114">Si no define un valor constante para el campo, utilice `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="e99bf-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="e99bf-115">[in] El valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="e99bf-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="e99bf-116">[in] El tamaño en caracteres (Unicode) de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="e99bf-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="e99bf-117">[out] El `mdFieldDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="e99bf-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e99bf-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e99bf-118">Requirements</span></span>  
 <span data-ttu-id="e99bf-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e99bf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e99bf-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e99bf-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e99bf-121">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e99bf-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e99bf-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e99bf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99bf-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e99bf-123">See Also</span></span>  
 [<span data-ttu-id="e99bf-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e99bf-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e99bf-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e99bf-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
