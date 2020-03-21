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
ms.openlocfilehash: 22141cf46a965c0624c076bd1d86d2624e5a09f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176024"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="58774-102">IMetaDataAssemblyImport::EnumManifestResources (Método)</span><span class="sxs-lookup"><span data-stu-id="58774-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="58774-103">Obtiene un puntero a un enumerador para los recursos a los que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="58774-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58774-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58774-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="58774-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58774-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="58774-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="58774-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="58774-107">Debe ser un valor `EnumManifestResources` nulo cuando se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="58774-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="58774-108">[fuera] Matriz utilizada para `mdManifestResource` almacenar los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="58774-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="58774-109">[en] El número `mdManifestResource` máximo de tokens `rManifestResources`que se pueden colocar en .</span><span class="sxs-lookup"><span data-stu-id="58774-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="58774-110">[fuera] El número `mdManifestResource` de tokens `rManifestResources`colocados en .</span><span class="sxs-lookup"><span data-stu-id="58774-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58774-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58774-111">Return Value</span></span>  
  
|<span data-ttu-id="58774-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58774-112">HRESULT</span></span>|<span data-ttu-id="58774-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="58774-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="58774-114">`EnumManifestResources`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="58774-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="58774-115">No hay tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="58774-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="58774-116">En este `pcTokens` caso, se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="58774-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58774-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58774-117">Requirements</span></span>  
 <span data-ttu-id="58774-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58774-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58774-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="58774-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58774-120">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58774-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58774-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58774-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58774-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58774-122">See also</span></span>

- [<span data-ttu-id="58774-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58774-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
