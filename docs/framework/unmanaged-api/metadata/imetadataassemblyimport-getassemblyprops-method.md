---
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
ms.openlocfilehash: dfa900e2184a8c415d75f5702c572b14c4018749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177783"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="4ab58-102">IMetaDataAssemblyImport::GetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="4ab58-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="4ab58-103">Obtiene el conjunto de propiedades del ensamblado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="4ab58-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ab58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ab58-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4ab58-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ab58-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="4ab58-106">[in].</span><span class="sxs-lookup"><span data-stu-id="4ab58-106">[in].</span></span> <span data-ttu-id="4ab58-107">El `mdAssembly` token de metadatos que representa el ensamblado para el que se obtienen las propiedades.</span><span class="sxs-lookup"><span data-stu-id="4ab58-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="4ab58-108">[fuera] Un puntero a la clave pública o al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4ab58-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="4ab58-109">[fuera] El número de bytes de la clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="4ab58-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="4ab58-110">[fuera] Puntero al algoritmo utilizado para aplicar hash a los archivos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4ab58-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="4ab58-111">[fuera] El nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4ab58-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4ab58-112">[en] El tamaño, en caracteres `szName`anchos, de .</span><span class="sxs-lookup"><span data-stu-id="4ab58-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4ab58-113">[fuera] El número de caracteres `szName`anchos realmente devueltos en .</span><span class="sxs-lookup"><span data-stu-id="4ab58-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="4ab58-114">[fuera] Puntero a una estructura ASSEMBLYMETADATA que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4ab58-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="4ab58-115">[fuera] Indicadores que describen los metadatos aplicados a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4ab58-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="4ab58-116">Este valor es una combinación de uno o más [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="4ab58-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ab58-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ab58-117">Requirements</span></span>  
 <span data-ttu-id="4ab58-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ab58-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ab58-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4ab58-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ab58-120">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ab58-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ab58-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ab58-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab58-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ab58-122">See also</span></span>

- [<span data-ttu-id="4ab58-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ab58-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
