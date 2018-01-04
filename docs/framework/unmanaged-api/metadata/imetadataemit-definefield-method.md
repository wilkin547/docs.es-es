---
title: "IMetaDataEmit::DefineField (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2c4b5604c3daec78744eb8902a30750571b9f82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="91a16-102">IMetaDataEmit::DefineField (Método)</span><span class="sxs-lookup"><span data-stu-id="91a16-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="91a16-103">Crea una definición para un campo con la firma de metadatos especificada y obtiene un símbolo (token) para esa definición de campo.</span><span class="sxs-lookup"><span data-stu-id="91a16-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91a16-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="91a16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91a16-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="91a16-106">[in] El `mdTypeDef` símbolo (token) para la interfaz o clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="91a16-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="91a16-107">[in] El nombre del campo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="91a16-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="91a16-108">[in] Los atributos del campo.</span><span class="sxs-lookup"><span data-stu-id="91a16-108">[in] The field attributes.</span></span> <span data-ttu-id="91a16-109">Se trata de una máscara de bits de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="91a16-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="91a16-110">[in] La firma del campo como un BLOB.</span><span class="sxs-lookup"><span data-stu-id="91a16-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="91a16-111">[in] El recuento de bytes en `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="91a16-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlage`  
 <span data-ttu-id="91a16-112">[in] El `ELEMENT_TYPE_`  *\**  para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="91a16-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="91a16-113">Se trata de un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="91a16-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="91a16-114">Si no define un valor constante para el campo, use `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="91a16-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="91a16-115">[in] El valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="91a16-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="91a16-116">[in] El tamaño en caracteres (Unicode) de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="91a16-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="91a16-117">[out] El `mdFieldDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="91a16-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a16-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91a16-118">Requirements</span></span>  
 <span data-ttu-id="91a16-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91a16-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a16-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="91a16-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91a16-121">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91a16-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91a16-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a16-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a16-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="91a16-123">See Also</span></span>  
 [<span data-ttu-id="91a16-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91a16-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="91a16-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91a16-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
