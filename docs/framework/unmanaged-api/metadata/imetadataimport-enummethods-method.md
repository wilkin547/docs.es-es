---
title: "IMetaDataImport::EnumMethods (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4052bcd07ec5abd3c560569b59600123350e810c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="ec819-102">IMetaDataImport::EnumMethods (Método)</span><span class="sxs-lookup"><span data-stu-id="ec819-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="ec819-103">Enumera los tokens de MethodDef que representan métodos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ec819-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec819-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec819-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec819-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec819-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ec819-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="ec819-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ec819-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="ec819-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="ec819-108">[in] Un token de TypeDef que representa el tipo con los métodos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="ec819-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="ec819-109">[out] La matriz para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="ec819-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ec819-110">[in] El tamaño máximo de MethodDef `rMethods` matriz.</span><span class="sxs-lookup"><span data-stu-id="ec819-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ec819-111">[out] El número de tokens de MethodDef devueltos en `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="ec819-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec819-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec819-112">Return Value</span></span>  
  
|<span data-ttu-id="ec819-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec819-113">HRESULT</span></span>|<span data-ttu-id="ec819-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec819-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ec819-115">`EnumMethods`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ec819-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ec819-116">No hay ningún tokens de MethodDef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="ec819-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="ec819-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="ec819-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec819-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec819-118">Requirements</span></span>  
 <span data-ttu-id="ec819-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec819-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec819-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec819-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec819-121">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec819-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec819-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec819-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec819-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec819-123">See Also</span></span>  
 [<span data-ttu-id="ec819-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec819-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ec819-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec819-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
