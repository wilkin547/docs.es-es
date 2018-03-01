---
title: "IMetaDataImport::EnumFields (Método)"
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
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1a4548494ffd766cbf10558121f5c2df6cf63cba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="42f6d-102">IMetaDataImport::EnumFields (Método)</span><span class="sxs-lookup"><span data-stu-id="42f6d-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="42f6d-103">Enumera los tokens de FieldDef del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="42f6d-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f6d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42f6d-104">Syntax</span></span>  
  
```  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42f6d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42f6d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="42f6d-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="42f6d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="42f6d-107">[in] El token de TypeDef de la clase cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="42f6d-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="42f6d-108">[out] La lista de tokens de FieldDef.</span><span class="sxs-lookup"><span data-stu-id="42f6d-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="42f6d-109">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="42f6d-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="42f6d-110">[out] El número real de los tokens de FieldDef devueltos en `rFields`.</span><span class="sxs-lookup"><span data-stu-id="42f6d-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42f6d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42f6d-111">Return Value</span></span>  
  
|<span data-ttu-id="42f6d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42f6d-112">HRESULT</span></span>|<span data-ttu-id="42f6d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="42f6d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="42f6d-114">`EnumFields`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="42f6d-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="42f6d-115">No hay ningún campo para enumerar.</span><span class="sxs-lookup"><span data-stu-id="42f6d-115">There are no fields to enumerate.</span></span> <span data-ttu-id="42f6d-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="42f6d-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42f6d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42f6d-117">Requirements</span></span>  
 <span data-ttu-id="42f6d-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42f6d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42f6d-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="42f6d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42f6d-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42f6d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42f6d-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42f6d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f6d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="42f6d-122">See Also</span></span>  
 [<span data-ttu-id="42f6d-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42f6d-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="42f6d-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42f6d-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
