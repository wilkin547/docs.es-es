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
ms.openlocfilehash: a90deaf3e9ddf326c6fca558cbb4681fc40e022d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009060"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="c1ec8-102">IMetaDataAssemblyImport::GetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="c1ec8-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="c1ec8-103">Obtiene el conjunto de propiedades para el ensamblado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="c1ec8-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ec8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1ec8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c1ec8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1ec8-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="c1ec8-106">[in].</span><span class="sxs-lookup"><span data-stu-id="c1ec8-106">[in].</span></span> <span data-ttu-id="c1ec8-107">`mdAssembly`Token de metadatos que representa el ensamblado para el que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c1ec8-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="c1ec8-108">enuncia Puntero a la clave pública o al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="c1ec8-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="c1ec8-109">enuncia Número de bytes de la clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="c1ec8-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="c1ec8-110">enuncia Puntero al algoritmo utilizado para aplicar un algoritmo hash a los archivos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c1ec8-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="c1ec8-111">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c1ec8-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c1ec8-112">de Tamaño, en caracteres anchos, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="c1ec8-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c1ec8-113">enuncia Número de caracteres anchos realmente devueltos en `szName` .</span><span class="sxs-lookup"><span data-stu-id="c1ec8-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="c1ec8-114">enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c1ec8-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="c1ec8-115">enuncia Marcas que describen los metadatos aplicados a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c1ec8-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="c1ec8-116">Este valor es una combinación de uno o más valores de [corassemblyflags (](corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="c1ec8-116">This value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ec8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1ec8-117">Requirements</span></span>  
 <span data-ttu-id="c1ec8-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ec8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ec8-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c1ec8-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1ec8-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c1ec8-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1ec8-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ec8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ec8-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1ec8-122">See also</span></span>

- [<span data-ttu-id="c1ec8-123">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1ec8-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
