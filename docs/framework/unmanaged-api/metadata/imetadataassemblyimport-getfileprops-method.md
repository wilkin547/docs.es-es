---
title: IMetaDataAssemblyImport::GetFileProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: dae4a36537eeac58ffb17ebc1b78d935ec807cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175985"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="9c66a-102">IMetaDataAssemblyImport::GetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="9c66a-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="9c66a-103">Obtiene las propiedades del archivo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="9c66a-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c66a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c66a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c66a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c66a-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="9c66a-106">[en] El `mdFile` token de metadatos que representa el archivo para el que se obtienen las propiedades.</span><span class="sxs-lookup"><span data-stu-id="9c66a-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="9c66a-107">[fuera] El nombre simple del archivo.</span><span class="sxs-lookup"><span data-stu-id="9c66a-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9c66a-108">[en] El tamaño, en caracteres `szName`anchos, de .</span><span class="sxs-lookup"><span data-stu-id="9c66a-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="9c66a-109">[fuera] El número de caracteres `szName`anchos realmente devueltos en .</span><span class="sxs-lookup"><span data-stu-id="9c66a-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="9c66a-110">[fuera] Un puntero al valor hash.</span><span class="sxs-lookup"><span data-stu-id="9c66a-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="9c66a-111">Este es el hash, usando el algoritmo SHA-1, del archivo.</span><span class="sxs-lookup"><span data-stu-id="9c66a-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="9c66a-112">[fuera] El número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="9c66a-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="9c66a-113">[fuera] Puntero a las marcas que describen los metadatos aplicados a un archivo.</span><span class="sxs-lookup"><span data-stu-id="9c66a-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="9c66a-114">El valor flags es una combinación de uno o varios [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="9c66a-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c66a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c66a-115">Requirements</span></span>  
 <span data-ttu-id="9c66a-116">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c66a-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c66a-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9c66a-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c66a-118">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c66a-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c66a-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c66a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c66a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c66a-120">See also</span></span>

- [<span data-ttu-id="9c66a-121">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c66a-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
