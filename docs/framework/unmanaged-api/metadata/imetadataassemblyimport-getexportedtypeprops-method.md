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
ms.openlocfilehash: 82302124828a2dab73b445128d7d847e112edd36
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448212"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="febaf-102">IMetaDataAssemblyImport::GetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="febaf-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="febaf-103">Obtiene el conjunto de propiedades del tipo exportado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="febaf-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="febaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="febaf-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="febaf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="febaf-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="febaf-106">de Un token de metadatos de `mdExportedType` que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="febaf-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="febaf-107">enuncia Nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="febaf-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="febaf-108">de Tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="febaf-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="febaf-109">enuncia Número de caracteres anchos realmente devueltos en `szName`</span><span class="sxs-lookup"><span data-stu-id="febaf-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="febaf-110">enuncia Un `mdFile`, `mdAssemblyRef`o `mdExportedType` token de metadatos que contiene o permite el acceso a las propiedades del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="febaf-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="febaf-111">enuncia Un puntero a un token de `mdTypeDef` que representa un tipo en el archivo.</span><span class="sxs-lookup"><span data-stu-id="febaf-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="febaf-112">enuncia Puntero a las marcas que describen los metadatos aplicados al tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="febaf-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="febaf-113">El valor de flags puede ser uno o varios valores de [cortypeattr (](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="febaf-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="febaf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="febaf-114">Requirements</span></span>  
 <span data-ttu-id="febaf-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="febaf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="febaf-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="febaf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="febaf-117">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="febaf-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="febaf-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="febaf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febaf-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="febaf-119">See also</span></span>

- [<span data-ttu-id="febaf-120">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="febaf-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
