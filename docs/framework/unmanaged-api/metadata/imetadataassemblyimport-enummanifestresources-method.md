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
ms.openlocfilehash: 560a6adf85fab7f421b86cba52224d5b1bfe1089
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006264"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="f75cb-102">IMetaDataAssemblyImport::EnumManifestResources (Método)</span><span class="sxs-lookup"><span data-stu-id="f75cb-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="f75cb-103">Obtiene un puntero a un enumerador para los recursos a los que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="f75cb-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f75cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f75cb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="f75cb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f75cb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f75cb-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="f75cb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f75cb-107">Debe ser un valor NULL cuando `EnumManifestResources` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f75cb-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="f75cb-108">enuncia Matriz utilizada para almacenar los `mdManifestResource` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f75cb-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f75cb-109">de Número máximo de `mdManifestResource` tokens que se pueden colocar en `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="f75cb-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f75cb-110">enuncia Número de `mdManifestResource` tokens realmente colocados en `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="f75cb-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f75cb-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f75cb-111">Return Value</span></span>  
  
|<span data-ttu-id="f75cb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f75cb-112">HRESULT</span></span>|<span data-ttu-id="f75cb-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f75cb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f75cb-114">`EnumManifestResources`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f75cb-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f75cb-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="f75cb-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f75cb-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="f75cb-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f75cb-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f75cb-117">Requirements</span></span>  
 <span data-ttu-id="f75cb-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f75cb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f75cb-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f75cb-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f75cb-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f75cb-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f75cb-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f75cb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75cb-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f75cb-122">See also</span></span>

- [<span data-ttu-id="f75cb-123">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f75cb-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
