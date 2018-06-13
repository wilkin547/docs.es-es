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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f147fef90d7a9033bdfd07b75e5c33efd2c6881f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444521"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="ba9b8-102">IMetaDataAssemblyImport::GetFileProps (Método)</span><span class="sxs-lookup"><span data-stu-id="ba9b8-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="ba9b8-103">Obtiene las propiedades del archivo con la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba9b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba9b8-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="ba9b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba9b8-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="ba9b8-106">[in] El `mdFile` símbolo (token) de metadatos que representa el archivo para el que se va a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="ba9b8-107">[out] El nombre simple del archivo.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ba9b8-108">[in] El tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ba9b8-109">[out] El número de caracteres anchos realmente devueltos en `szName`.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="ba9b8-110">[out] Un puntero con el valor hash.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="ba9b8-111">Este es el valor de hash, utilizando el algoritmo SHA-1, del archivo.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="ba9b8-112">[out] El número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="ba9b8-113">[out] Un puntero a los marcadores que describen los metadatos aplicados a un archivo.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="ba9b8-114">El valor de flags es una combinación de uno o varios [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="ba9b8-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba9b8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba9b8-115">Requirements</span></span>  
 <span data-ttu-id="ba9b8-116">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba9b8-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba9b8-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba9b8-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba9b8-118">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba9b8-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba9b8-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba9b8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba9b8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba9b8-120">See Also</span></span>  
 [<span data-ttu-id="ba9b8-121">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba9b8-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
