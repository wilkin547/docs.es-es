---
title: "IMetaDataAssemblyImport::EnumFiles (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ce0682f6f7719c902183778578d75dd19d56867
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="4c8f8-102">IMetaDataAssemblyImport::EnumFiles (Método)</span><span class="sxs-lookup"><span data-stu-id="4c8f8-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="4c8f8-103">Enumera los archivos que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c8f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c8f8-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c8f8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4c8f8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4c8f8-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4c8f8-107">Debe ser un valor null para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="4c8f8-108">[out] La matriz que se utiliza para almacenar el `mdFile` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4c8f8-109">[in] El número máximo de `mdFile` tokens que se pueden colocar en `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4c8f8-110">[out] El número de `mdFile` tokens realmente se colocan en `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c8f8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4c8f8-111">Return Value</span></span>  
  
|<span data-ttu-id="4c8f8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4c8f8-112">HRESULT</span></span>|<span data-ttu-id="4c8f8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c8f8-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4c8f8-114">`EnumFiles`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4c8f8-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4c8f8-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="4c8f8-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c8f8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c8f8-117">Requirements</span></span>  
 <span data-ttu-id="4c8f8-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c8f8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c8f8-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4c8f8-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c8f8-120">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c8f8-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4c8f8-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c8f8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c8f8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c8f8-122">See Also</span></span>  
 [<span data-ttu-id="4c8f8-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c8f8-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
