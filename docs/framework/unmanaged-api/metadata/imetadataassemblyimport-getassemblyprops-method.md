---
description: 'Más información sobre: IMetaDataAssemblyImport:: Getassemblyprops ((método)'
title: IMetaDataAssemblyImport::GetAssemblyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: 9cd3674dcd640bce27ae5d399d0f7de0c2eeca48
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784150"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="841d9-103">IMetaDataAssemblyImport::GetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="841d9-103">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>

<span data-ttu-id="841d9-104">Obtiene el conjunto de propiedades para el ensamblado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="841d9-104">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="841d9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="841d9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="841d9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="841d9-106">Parameters</span></span>  

 `mda`  
 <span data-ttu-id="841d9-107">[in].</span><span class="sxs-lookup"><span data-stu-id="841d9-107">[in].</span></span> <span data-ttu-id="841d9-108">`mdAssembly`Token de metadatos que representa el ensamblado para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="841d9-108">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="841d9-109">enuncia Puntero a la clave pública o al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="841d9-109">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="841d9-110">enuncia Número de bytes de la clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="841d9-110">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="841d9-111">enuncia Puntero al algoritmo utilizado para aplicar un algoritmo hash a los archivos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="841d9-111">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="841d9-112">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="841d9-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="841d9-113">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="841d9-113">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="841d9-114">enuncia Número de caracteres anchos realmente devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="841d9-114">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="841d9-115">enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="841d9-115">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="841d9-116">enuncia Marcas que describen los metadatos aplicados a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="841d9-116">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="841d9-117">Este valor es una combinación de uno o más valores de [corassemblyflags (](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="841d9-117">This value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="841d9-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="841d9-118">Requirements</span></span>  

 <span data-ttu-id="841d9-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="841d9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="841d9-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="841d9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="841d9-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="841d9-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="841d9-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="841d9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841d9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="841d9-123">See also</span></span>

- [<span data-ttu-id="841d9-124">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="841d9-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
