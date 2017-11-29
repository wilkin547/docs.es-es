---
title: "IMetaDataImport::EnumMethodImpls (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodImpls
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2634642c49c9d95765b6a93048a04ce512b28099
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="dd95f-102">IMetaDataImport::EnumMethodImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="dd95f-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="dd95f-103">Enumera los tokens MethodBody y MethodDeclaration que representan métodos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="dd95f-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd95f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd95f-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdToken     rMethodBody[],   
   [out]     mdToken     rMethodDecl[],   
   [in]      ULONG       cMax,   
   [in]      ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd95f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd95f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="dd95f-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="dd95f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="dd95f-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="dd95f-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="dd95f-108">[in] Símbolo (token) de una definición de tipo para el tipo cuyas implementaciones de método para enumerar.</span><span class="sxs-lookup"><span data-stu-id="dd95f-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="dd95f-109">[out] La matriz para almacenar los tokens MethodBody.</span><span class="sxs-lookup"><span data-stu-id="dd95f-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="dd95f-110">[out] La matriz para almacenar los símbolos (tokens) de MethodDeclaration.</span><span class="sxs-lookup"><span data-stu-id="dd95f-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dd95f-111">[in] El tamaño máximo de la `rMethodBody` y `rMethodDecl` matrices.</span><span class="sxs-lookup"><span data-stu-id="dd95f-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="dd95f-112">[in] El número real de métodos devueltos en `rMethodBody` y `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="dd95f-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd95f-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd95f-113">Return Value</span></span>  
  
|<span data-ttu-id="dd95f-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd95f-114">HRESULT</span></span>|<span data-ttu-id="dd95f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd95f-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="dd95f-116">`EnumMethodImpls`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dd95f-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="dd95f-117">No hay ningún tokens de método que enumerar.</span><span class="sxs-lookup"><span data-stu-id="dd95f-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="dd95f-118">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="dd95f-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd95f-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd95f-119">Requirements</span></span>  
 <span data-ttu-id="dd95f-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd95f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd95f-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd95f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd95f-122">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd95f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd95f-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd95f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd95f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd95f-124">See Also</span></span>  
 [<span data-ttu-id="dd95f-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd95f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="dd95f-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd95f-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
