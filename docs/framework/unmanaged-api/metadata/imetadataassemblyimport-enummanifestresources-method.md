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
ms.openlocfilehash: 2748460826deb422a3851713db11343209fe449a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449558"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="a5cb9-102">IMetaDataAssemblyImport::EnumManifestResources (Método)</span><span class="sxs-lookup"><span data-stu-id="a5cb9-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="a5cb9-103">Obtiene un puntero a un enumerador para los recursos a los que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5cb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5cb9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a5cb9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5cb9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a5cb9-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a5cb9-107">Debe ser un valor NULL cuando se llama al método `EnumManifestResources` por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="a5cb9-108">enuncia Matriz usada para almacenar los tokens de metadatos de `mdManifestResource`.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a5cb9-109">de Número máximo de tokens de `mdManifestResource` que se pueden colocar en `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a5cb9-110">enuncia Número de tokens de `mdManifestResource` realmente colocados en `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5cb9-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a5cb9-111">Return Value</span></span>  
  
|<span data-ttu-id="a5cb9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5cb9-112">HRESULT</span></span>|<span data-ttu-id="a5cb9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5cb9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a5cb9-114">`EnumManifestResources` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a5cb9-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a5cb9-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="a5cb9-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5cb9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5cb9-117">Requirements</span></span>  
 <span data-ttu-id="a5cb9-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5cb9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5cb9-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a5cb9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5cb9-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a5cb9-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5cb9-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5cb9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5cb9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5cb9-122">See also</span></span>

- [<span data-ttu-id="a5cb9-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5cb9-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
