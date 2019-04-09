---
title: IMetaDataAssemblyImport::GetExportedTypeProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91b1e4469f07954dc433769911c78d72bb3c36cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096155"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="e4492-102">IMetaDataAssemblyImport::GetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e4492-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="e4492-103">Obtiene el conjunto de propiedades del tipo exportado con la firma de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="e4492-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4492-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4492-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e4492-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4492-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="e4492-106">[in] Un `mdExportedType` token de metadatos que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="e4492-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="e4492-107">[out] El nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="e4492-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e4492-108">[in] El tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="e4492-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="e4492-109">[out] El número de caracteres anchos realmente devueltos en</span><span class="sxs-lookup"><span data-stu-id="e4492-109">[out] The number of wide characters actually returned in</span></span> `szName`  
  
 `ptkImplementation`  
 <span data-ttu-id="e4492-110">[out] Un `mdFile`, `mdAssemblyRef`, o `mdExportedType` token de metadatos que contiene o permite el acceso a las propiedades del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="e4492-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="e4492-111">[out] Un puntero a un `mdTypeDef` token que representa un tipo en el archivo.</span><span class="sxs-lookup"><span data-stu-id="e4492-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="e4492-112">[out] Un puntero a los marcadores que describen los metadatos aplicados al tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="e4492-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="e4492-113">El valor de marcas puede ser uno o más [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="e4492-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4492-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4492-114">Requirements</span></span>  
 <span data-ttu-id="e4492-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4492-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4492-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e4492-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4492-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e4492-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e4492-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e4492-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e4492-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4492-119">See also</span></span>

- [<span data-ttu-id="e4492-120">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4492-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
