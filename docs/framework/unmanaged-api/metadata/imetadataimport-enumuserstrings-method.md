---
title: IMetaDataImport::EnumUserStrings (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98b99493e54b123d37eb281455180b9a25baddd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446835"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="1be21-102">IMetaDataImport::EnumUserStrings (Método)</span><span class="sxs-lookup"><span data-stu-id="1be21-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="1be21-103">Enumera los tokens de String que representan las cadenas codificadas de forma rígida en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="1be21-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1be21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1be21-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1be21-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1be21-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1be21-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="1be21-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1be21-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="1be21-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="1be21-108">[out] La matriz que se utiliza para almacenar los tokens de String.</span><span class="sxs-lookup"><span data-stu-id="1be21-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1be21-109">[in] Tamaño máximo de la matriz `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="1be21-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="1be21-110">[out] El número de tokens de String que se devuelve en `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="1be21-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1be21-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1be21-111">Return Value</span></span>  
  
|<span data-ttu-id="1be21-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1be21-112">HRESULT</span></span>|<span data-ttu-id="1be21-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1be21-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1be21-114">`EnumUserStrings` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1be21-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1be21-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="1be21-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="1be21-116">En ese caso, `pcStrings` es cero.</span><span class="sxs-lookup"><span data-stu-id="1be21-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1be21-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1be21-117">Remarks</span></span>  
 <span data-ttu-id="1be21-118">Los tokens de String se crean mediante el [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1be21-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="1be21-119">Este método está diseñado para utilizarse con un explorador de metadatos en lugar de mediante un compilador.</span><span class="sxs-lookup"><span data-stu-id="1be21-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1be21-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1be21-120">Requirements</span></span>  
 <span data-ttu-id="1be21-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1be21-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1be21-122">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1be21-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1be21-123">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1be21-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1be21-124">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1be21-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be21-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1be21-125">See Also</span></span>  
 [<span data-ttu-id="1be21-126">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1be21-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1be21-127">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1be21-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
