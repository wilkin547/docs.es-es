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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1beb76012d5f0351ee644c8dea89cabdbe2c8970
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555029"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="58da3-102">IMetaDataAssemblyImport::EnumExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="58da3-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="58da3-103">Enumera los tipos exportados hace referencia en el manifiesto del ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="58da3-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58da3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58da3-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58da3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58da3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="58da3-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="58da3-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="58da3-107">Esto debe ser un valor null valor cuando el `EnumExportedTypes` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="58da3-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="58da3-108">[out] La enumeración de `mdExportedType` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="58da3-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="58da3-109">[in] El número máximo de `mdExportedType` tokens que se pueden colocar en el `rExportedTypes` matriz.</span><span class="sxs-lookup"><span data-stu-id="58da3-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="58da3-110">[out] El número de `mdExportedType` tokens realmente están colocan en `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="58da3-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58da3-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58da3-111">Return Value</span></span>  
  
|<span data-ttu-id="58da3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58da3-112">HRESULT</span></span>|<span data-ttu-id="58da3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="58da3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="58da3-114">`EnumExportedTypes` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="58da3-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="58da3-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="58da3-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="58da3-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="58da3-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58da3-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58da3-117">Requirements</span></span>  
 <span data-ttu-id="58da3-118">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58da3-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58da3-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="58da3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58da3-120">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58da3-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58da3-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58da3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58da3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="58da3-122">See also</span></span>
- [<span data-ttu-id="58da3-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58da3-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
