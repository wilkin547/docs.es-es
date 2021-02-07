---
description: 'Más información sobre: IMetaDataAssemblyImport:: EnumManifestResources ((método)'
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
ms.openlocfilehash: ff819ebb575626af6049558656637e7fabcbc322
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677988"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="6e220-103">IMetaDataAssemblyImport::EnumManifestResources (Método)</span><span class="sxs-lookup"><span data-stu-id="6e220-103">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>

<span data-ttu-id="6e220-104">Obtiene un puntero a un enumerador para los recursos a los que se hace referencia en el manifiesto del ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="6e220-104">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e220-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e220-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="6e220-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6e220-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="6e220-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="6e220-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6e220-108">Debe ser un valor NULL cuando `EnumManifestResources` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="6e220-108">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="6e220-109">enuncia Matriz utilizada para almacenar los `mdManifestResource` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6e220-109">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6e220-110">de Número máximo de `mdManifestResource` tokens que se pueden colocar en `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="6e220-110">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6e220-111">enuncia Número de `mdManifestResource` tokens realmente colocados en `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="6e220-111">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e220-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6e220-112">Return Value</span></span>  
  
|<span data-ttu-id="6e220-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6e220-113">HRESULT</span></span>|<span data-ttu-id="6e220-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e220-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6e220-115">`EnumManifestResources` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6e220-115">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6e220-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="6e220-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="6e220-117">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="6e220-117">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e220-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e220-118">Requirements</span></span>  

 <span data-ttu-id="6e220-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e220-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e220-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6e220-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e220-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e220-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e220-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e220-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e220-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e220-123">See also</span></span>

- [<span data-ttu-id="6e220-124">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e220-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
