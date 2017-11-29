---
title: "IMetaDataAssemblyImport::EnumManifestResources (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumManifestResources
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25d8b63e2f40566164274715e562960eafbb83e5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="ed0b9-102">IMetaDataAssemblyImport::EnumManifestResources (Método)</span><span class="sxs-lookup"><span data-stu-id="ed0b9-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="ed0b9-103">Obtiene un puntero a un enumerador para los recursos que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed0b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed0b9-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed0b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed0b9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ed0b9-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ed0b9-107">Debe ser un valor null valor cuando el `EnumManifestResources` método se llama por primera vez.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="ed0b9-108">[out] La matriz que se utiliza para almacenar el `mdManifestResource` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ed0b9-109">[in] El número máximo de `mdManifestResource` tokens que se pueden colocar en `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ed0b9-110">[out] El número de `mdManifestResource` tokens realmente se colocan en `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed0b9-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed0b9-111">Return Value</span></span>  
  
|<span data-ttu-id="ed0b9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed0b9-112">HRESULT</span></span>|<span data-ttu-id="ed0b9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed0b9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ed0b9-114">`EnumManifestResources`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ed0b9-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ed0b9-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="ed0b9-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed0b9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed0b9-117">Requirements</span></span>  
 <span data-ttu-id="ed0b9-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed0b9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed0b9-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ed0b9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed0b9-120">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed0b9-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed0b9-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed0b9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0b9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed0b9-122">See Also</span></span>  
 [<span data-ttu-id="ed0b9-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed0b9-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
