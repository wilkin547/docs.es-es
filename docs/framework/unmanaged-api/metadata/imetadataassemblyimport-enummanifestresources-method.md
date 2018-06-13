---
title: IMetaDataAssemblyImport::EnumManifestResources (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 707e482a6952ee1266950dc181fbc85e5d6ef398
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448060"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="8f46f-102">IMetaDataAssemblyImport::EnumManifestResources (Método)</span><span class="sxs-lookup"><span data-stu-id="8f46f-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="8f46f-103">Obtiene un puntero a un enumerador para los recursos que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="8f46f-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f46f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f46f-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f46f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f46f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8f46f-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="8f46f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8f46f-107">Debe ser un valor null valor cuando el `EnumManifestResources` método se llama por primera vez.</span><span class="sxs-lookup"><span data-stu-id="8f46f-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="8f46f-108">[out] La matriz que se utiliza para almacenar el `mdManifestResource` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="8f46f-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8f46f-109">[in] El número máximo de `mdManifestResource` tokens que se pueden colocar en `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="8f46f-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8f46f-110">[out] El número de `mdManifestResource` tokens realmente se colocan en `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="8f46f-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f46f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8f46f-111">Return Value</span></span>  
  
|<span data-ttu-id="8f46f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f46f-112">HRESULT</span></span>|<span data-ttu-id="8f46f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f46f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8f46f-114">`EnumManifestResources` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8f46f-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8f46f-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="8f46f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="8f46f-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="8f46f-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f46f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f46f-117">Requirements</span></span>  
 <span data-ttu-id="8f46f-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f46f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f46f-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8f46f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f46f-120">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f46f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f46f-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f46f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f46f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f46f-122">See Also</span></span>  
 [<span data-ttu-id="8f46f-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f46f-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
