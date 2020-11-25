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
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722107"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="edbb0-102">IMetaDataAssemblyImport::GetExportedTypeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="edbb0-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>

<span data-ttu-id="edbb0-103">Obtiene el conjunto de propiedades del tipo exportado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="edbb0-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edbb0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edbb0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="edbb0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="edbb0-105">Parameters</span></span>  

 `mdct`  
 <span data-ttu-id="edbb0-106">de `mdExportedType` Token de metadatos que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="edbb0-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="edbb0-107">enuncia Nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="edbb0-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="edbb0-108">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="edbb0-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="edbb0-109">enuncia Número de caracteres anchos realmente devueltos en `szName`</span><span class="sxs-lookup"><span data-stu-id="edbb0-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="edbb0-110">enuncia Un `mdFile` `mdAssemblyRef` `mdExportedType` token de metadatos, o que contiene o permite el acceso a las propiedades del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="edbb0-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="edbb0-111">enuncia Un puntero a un `mdTypeDef` token que representa un tipo en el archivo.</span><span class="sxs-lookup"><span data-stu-id="edbb0-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="edbb0-112">enuncia Puntero a las marcas que describen los metadatos aplicados al tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="edbb0-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="edbb0-113">El valor de flags puede ser uno o varios valores de [cortypeattr (](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="edbb0-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edbb0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="edbb0-114">Requirements</span></span>  

 <span data-ttu-id="edbb0-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edbb0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edbb0-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="edbb0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edbb0-117">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="edbb0-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="edbb0-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edbb0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edbb0-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edbb0-119">See also</span></span>

- [<span data-ttu-id="edbb0-120">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edbb0-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
