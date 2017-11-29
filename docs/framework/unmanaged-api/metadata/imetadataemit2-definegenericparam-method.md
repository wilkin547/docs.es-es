---
title: "IMetaDataEmit2::DefineGenericParam (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.DefineGenericParam
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 737e57b86e74cc7e4668589d16c2e2cb351162bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="b29f7-102">IMetaDataEmit2::DefineGenericParam (Método)</span><span class="sxs-lookup"><span data-stu-id="b29f7-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="b29f7-103">Crea una definición para un parámetro de tipo genérico y obtiene un símbolo (token) para ese parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="b29f7-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b29f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b29f7-104">Syntax</span></span>  
  
```  
HRESULT DefineGenericParam (   
    [in]  mdToken         tk,   
    [in]  ULONG           ulParamSeq,   
    [in]  DWORD           dwParamFlags,   
    [in]  LPCWSTR         szname,   
    [in]  DWORD           reserved,   
    [in]  mdToken         rtkConstraints[],   
    [out] mdGenericParam  *pgp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b29f7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b29f7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b29f7-106">[in] Un `mdTypeDef` o `mdMethodDef` símbolo (token) que representa el método o constructor para el que se va a definir un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="b29f7-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="b29f7-107">[in] El índice del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="b29f7-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="b29f7-108">[in] Un valor de la [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeración que describe el tipo del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="b29f7-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="b29f7-109">[in] El nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="b29f7-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="b29f7-110">[in] Este parámetro está reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="b29f7-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="b29f7-111">[in] Una matriz terminada en cero de restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="b29f7-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="b29f7-112">Miembros de la matriz deben ser un `mdTypeDef`, `mdTypeRef`, o `mdTypeSpec` token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b29f7-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="b29f7-113">[out] Un token que representa el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="b29f7-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b29f7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b29f7-114">Requirements</span></span>  
 <span data-ttu-id="b29f7-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b29f7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b29f7-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b29f7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b29f7-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b29f7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b29f7-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b29f7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29f7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b29f7-119">See Also</span></span>  
 [<span data-ttu-id="b29f7-120">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b29f7-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="b29f7-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b29f7-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
