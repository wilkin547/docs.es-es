---
title: "IMetaDataAssemblyImport::EnumExportedTypes (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumExportedTypes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54b5a51dc0a12bb4c159b61252c9db0a82f03518
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="6251f-102">IMetaDataAssemblyImport::EnumExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="6251f-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="6251f-103">Enumera los tipos exportados al que hace referencia en el manifiesto del ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="6251f-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6251f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6251f-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6251f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6251f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6251f-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="6251f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6251f-107">Debe ser un valor null valor cuando el `EnumExportedTypes` método se llama por primera vez.</span><span class="sxs-lookup"><span data-stu-id="6251f-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="6251f-108">[out] La enumeración de `mdExportedType` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6251f-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6251f-109">[in] El número máximo de `mdExportedType` tokens que se pueden colocar en el `rExportedTypes` matriz.</span><span class="sxs-lookup"><span data-stu-id="6251f-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6251f-110">[out] El número de `mdExportedType` tokens realmente se colocan en `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="6251f-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6251f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6251f-111">Return Value</span></span>  
  
|<span data-ttu-id="6251f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6251f-112">HRESULT</span></span>|<span data-ttu-id="6251f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6251f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6251f-114">`EnumExportedTypes`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6251f-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6251f-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="6251f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="6251f-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="6251f-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6251f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6251f-117">Requirements</span></span>  
 <span data-ttu-id="6251f-118">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6251f-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6251f-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6251f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6251f-120">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6251f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6251f-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6251f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6251f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6251f-122">See Also</span></span>  
 [<span data-ttu-id="6251f-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6251f-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
