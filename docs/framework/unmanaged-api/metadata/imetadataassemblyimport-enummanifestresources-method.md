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
ms.openlocfilehash: a13e750029fed2f2261064dd69d6c1d800d59989
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473908"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="fb3b1-102">IMetaDataAssemblyImport::EnumManifestResources (Método)</span><span class="sxs-lookup"><span data-stu-id="fb3b1-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="fb3b1-103">Obtiene un puntero a un enumerador para los recursos que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb3b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb3b1-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="fb3b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb3b1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fb3b1-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fb3b1-107">Esto debe ser un valor null valor cuando el `EnumManifestResources` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="fb3b1-108">[out] Matriz utilizada para almacenar el `mdManifestResource` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fb3b1-109">[in] El número máximo de `mdManifestResource` tokens que se pueden colocar en `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fb3b1-110">[out] El número de `mdManifestResource` tokens realmente están colocan en `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb3b1-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fb3b1-111">Return Value</span></span>  
  
|<span data-ttu-id="fb3b1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb3b1-112">HRESULT</span></span>|<span data-ttu-id="fb3b1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb3b1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fb3b1-114">`EnumManifestResources` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fb3b1-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fb3b1-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="fb3b1-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb3b1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb3b1-117">Requirements</span></span>  
 <span data-ttu-id="fb3b1-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb3b1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb3b1-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb3b1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb3b1-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb3b1-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb3b1-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb3b1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3b1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb3b1-122">See also</span></span>
- [<span data-ttu-id="fb3b1-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb3b1-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
