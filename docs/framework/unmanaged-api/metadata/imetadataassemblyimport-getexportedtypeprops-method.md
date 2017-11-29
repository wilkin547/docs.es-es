---
title: "IMetaDataAssemblyImport::GetExportedTypeProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetExportedTypeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e142d0c77493ac1e9ab2bf485d8e111af4fb3ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="43861-102">IMetaDataAssemblyImport::GetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="43861-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="43861-103">Obtiene el conjunto de propiedades del tipo exportado con la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="43861-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43861-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43861-104">Syntax</span></span>  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43861-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43861-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="43861-106">[in] Un `mdExportedType` símbolo (token) de metadatos que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="43861-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="43861-107">[out] El nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="43861-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="43861-108">[in] El tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="43861-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="43861-109">[out] El número de caracteres anchos realmente devueltos en`szName`</span><span class="sxs-lookup"><span data-stu-id="43861-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="43861-110">[out] Un `mdFile`, `mdAssemblyRef`, o `mdExportedType` símbolo (token) de metadatos que contiene o permite el acceso a las propiedades del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="43861-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="43861-111">[out] Un puntero a un `mdTypeDef` símbolo (token) que representa un tipo en el archivo.</span><span class="sxs-lookup"><span data-stu-id="43861-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="43861-112">[out] Un puntero a las marcas que describen los metadatos aplicados al tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="43861-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="43861-113">El valor de marcas puede ser uno o más [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="43861-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43861-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43861-114">Requirements</span></span>  
 <span data-ttu-id="43861-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43861-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43861-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="43861-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43861-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43861-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43861-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43861-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43861-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="43861-119">See Also</span></span>  
 [<span data-ttu-id="43861-120">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43861-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
