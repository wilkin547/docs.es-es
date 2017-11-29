---
title: "IMetaDataAssemblyImport::EnumAssemblyRefs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumAssemblyRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 24a289ed42a99cd26c7829d9a5789ac3027026c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="e5abe-102">IMetaDataAssemblyImport::EnumAssemblyRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="e5abe-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="e5abe-103">Enumera la `mdAssemblyRef` instancias que se definen en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e5abe-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5abe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5abe-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5abe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5abe-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e5abe-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="e5abe-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e5abe-107">Debe ser un valor null valor cuando el `EnumAssemblyRefs` método se llama por primera vez.</span><span class="sxs-lookup"><span data-stu-id="e5abe-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="e5abe-108">[out] La enumeración de `mdAssemblyRef` los tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e5abe-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e5abe-109">[in] El número máximo de tokens que se pueden colocar en el `rAssemblyRefs` matriz.</span><span class="sxs-lookup"><span data-stu-id="e5abe-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e5abe-110">[out] El número de símbolos (tokens) realizó en `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="e5abe-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5abe-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5abe-111">Return Value</span></span>  
  
|<span data-ttu-id="e5abe-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5abe-112">HRESULT</span></span>|<span data-ttu-id="e5abe-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5abe-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e5abe-114">`EnumAssemblyRefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5abe-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e5abe-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="e5abe-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e5abe-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="e5abe-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5abe-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5abe-117">Requirements</span></span>  
 <span data-ttu-id="e5abe-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5abe-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5abe-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e5abe-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5abe-120">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5abe-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5abe-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5abe-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5abe-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5abe-122">See Also</span></span>  
 [<span data-ttu-id="e5abe-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5abe-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
