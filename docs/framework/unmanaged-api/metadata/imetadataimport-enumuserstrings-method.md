---
title: "IMetaDataImport::EnumUserStrings (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUserStrings
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d9c802318203db2ccd6043cded3c7730b18b0cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="e77bf-102">IMetaDataImport::EnumUserStrings (Método)</span><span class="sxs-lookup"><span data-stu-id="e77bf-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="e77bf-103">Enumera los tokens de String que representan las cadenas codificadas de forma rígida en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="e77bf-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e77bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e77bf-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e77bf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e77bf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e77bf-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="e77bf-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e77bf-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="e77bf-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="e77bf-108">[out] La matriz que se utiliza para almacenar los tokens de String.</span><span class="sxs-lookup"><span data-stu-id="e77bf-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e77bf-109">[in] Tamaño máximo de la matriz `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="e77bf-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="e77bf-110">[out] El número de tokens de String que se devuelve en `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="e77bf-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e77bf-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e77bf-111">Return Value</span></span>  
  
|<span data-ttu-id="e77bf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e77bf-112">HRESULT</span></span>|<span data-ttu-id="e77bf-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e77bf-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e77bf-114">`EnumUserStrings`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e77bf-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e77bf-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="e77bf-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e77bf-116">En ese caso, `pcStrings` es cero.</span><span class="sxs-lookup"><span data-stu-id="e77bf-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e77bf-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e77bf-117">Remarks</span></span>  
 <span data-ttu-id="e77bf-118">Los tokens de String se crean mediante el [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="e77bf-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="e77bf-119">Este método está diseñado para utilizarse con un explorador de metadatos en lugar de mediante un compilador.</span><span class="sxs-lookup"><span data-stu-id="e77bf-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e77bf-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e77bf-120">Requirements</span></span>  
 <span data-ttu-id="e77bf-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e77bf-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e77bf-122">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e77bf-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e77bf-123">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e77bf-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e77bf-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e77bf-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77bf-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e77bf-125">See Also</span></span>  
 [<span data-ttu-id="e77bf-126">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e77bf-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e77bf-127">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e77bf-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
