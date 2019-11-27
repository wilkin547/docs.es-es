---
title: IMetaDataAssemblyImport::GetManifestResourceProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: c1792ed0f15f8cfb62567593c9694453650f0bb9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436321"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="be35c-102">IMetaDataAssemblyImport::GetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="be35c-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="be35c-103">Obtiene el conjunto de propiedades del recurso de manifiesto con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="be35c-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be35c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be35c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be35c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be35c-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="be35c-106">de `mdManifestResource` token que representa el recurso para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="be35c-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="be35c-107">enuncia Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="be35c-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="be35c-108">de Tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="be35c-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="be35c-109">enuncia Puntero al número de caracteres anchos que se devuelven realmente en `szName`.</span><span class="sxs-lookup"><span data-stu-id="be35c-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="be35c-110">enuncia Un puntero a un token de `mdFile` o un token de `mdAssemblyRef` que representa el archivo o ensamblado, respectivamente, que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="be35c-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="be35c-111">enuncia Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="be35c-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="be35c-112">enuncia Puntero a las marcas que describen los metadatos aplicados a un recurso.</span><span class="sxs-lookup"><span data-stu-id="be35c-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="be35c-113">El valor de flags es una combinación de uno o más valores de [CorManifestResourceFlags (](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="be35c-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be35c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be35c-114">Requirements</span></span>  
 <span data-ttu-id="be35c-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be35c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be35c-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="be35c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be35c-117">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="be35c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be35c-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be35c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be35c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="be35c-119">See also</span></span>

- [<span data-ttu-id="be35c-120">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="be35c-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
