---
description: 'Más información sobre: IMetaDataAssemblyImport:: Getmanifestresourceprops ((método)'
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
ms.openlocfilehash: d8f390f8eede5153df282cc30479ceff22fb552d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728293"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="8d3bb-103">IMetaDataAssemblyImport::GetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="8d3bb-103">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>

<span data-ttu-id="8d3bb-104">Obtiene el conjunto de propiedades del recurso de manifiesto con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="8d3bb-104">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3bb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d3bb-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8d3bb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d3bb-106">Parameters</span></span>  

 `mdmr`  
 <span data-ttu-id="8d3bb-107">de `mdManifestResource` Token que representa el recurso para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="8d3bb-107">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="8d3bb-108">enuncia Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="8d3bb-108">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8d3bb-109">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="8d3bb-109">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="8d3bb-110">enuncia Puntero al número de caracteres anchos realmente devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="8d3bb-110">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="8d3bb-111">enuncia Un puntero a un `mdFile` token o `mdAssemblyRef` token que representa el archivo o ensamblado, respectivamente, que contiene el recurso.</span><span class="sxs-lookup"><span data-stu-id="8d3bb-111">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="8d3bb-112">enuncia Un puntero a un valor que especifica el desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="8d3bb-112">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="8d3bb-113">enuncia Puntero a las marcas que describen los metadatos aplicados a un recurso.</span><span class="sxs-lookup"><span data-stu-id="8d3bb-113">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="8d3bb-114">El valor de flags es una combinación de uno o más valores de [CorManifestResourceFlags (](cormanifestresourceflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="8d3bb-114">The flags value is a combination of one or more [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d3bb-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d3bb-115">Requirements</span></span>  

 <span data-ttu-id="8d3bb-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d3bb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d3bb-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8d3bb-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d3bb-118">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d3bb-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8d3bb-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d3bb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3bb-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d3bb-120">See also</span></span>

- [<span data-ttu-id="8d3bb-121">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d3bb-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
