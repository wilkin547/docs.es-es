---
title: IMetaDataAssemblyImport::EnumExportedTypes (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: f00fe5bce2f808265add228406dfaa2ccc267545
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176011"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="5adcf-102">IMetaDataAssemblyImport::EnumExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="5adcf-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="5adcf-103">Enumera los tipos exportados a los que se hace referencia en el manifiesto del ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="5adcf-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5adcf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5adcf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5adcf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5adcf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5adcf-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="5adcf-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5adcf-107">Debe ser un valor `EnumExportedTypes` nulo cuando se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5adcf-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="5adcf-108">[fuera] La enumeración de tokens de `mdExportedType` metadatos.</span><span class="sxs-lookup"><span data-stu-id="5adcf-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5adcf-109">[en] El número `mdExportedType` máximo de tokens que `rExportedTypes` se pueden colocar en la matriz.</span><span class="sxs-lookup"><span data-stu-id="5adcf-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5adcf-110">[fuera] El número `mdExportedType` de tokens `rExportedTypes`colocados en .</span><span class="sxs-lookup"><span data-stu-id="5adcf-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5adcf-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5adcf-111">Return Value</span></span>  
  
|<span data-ttu-id="5adcf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5adcf-112">HRESULT</span></span>|<span data-ttu-id="5adcf-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5adcf-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5adcf-114">`EnumExportedTypes`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="5adcf-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5adcf-115">No hay tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="5adcf-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="5adcf-116">En este `pcTokens` caso, se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="5adcf-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5adcf-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5adcf-117">Requirements</span></span>  
 <span data-ttu-id="5adcf-118">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5adcf-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5adcf-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5adcf-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5adcf-120">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5adcf-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5adcf-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5adcf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5adcf-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5adcf-122">See also</span></span>

- [<span data-ttu-id="5adcf-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5adcf-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
