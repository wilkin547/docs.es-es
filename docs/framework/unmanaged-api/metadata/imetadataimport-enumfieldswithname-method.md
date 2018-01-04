---
title: "IMetaDataImport::EnumFieldsWithName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumFieldsWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77b5ba7e191d9aa0f1587e4ac1ec25e655c27b14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="2e4e8-102">IMetaDataImport::EnumFieldsWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="2e4e8-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="2e4e8-103">Enumera los tokens de FieldDef del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e4e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e4e8-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e4e8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e4e8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2e4e8-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="2e4e8-107">[in] El token de tipo cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="2e4e8-108">[in] El nombre del campo que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="2e4e8-109">[out] Matriz que se utiliza para almacenar los tokens de FieldDef.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2e4e8-110">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2e4e8-111">[out] El número real de los tokens de FieldDef devueltos en `rFields`.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e4e8-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e4e8-112">Remarks</span></span>  
 <span data-ttu-id="2e4e8-113">A diferencia de [IMetaDataImport:: EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` descarta todos los tokens de campo que no tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e4e8-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2e4e8-114">Return Value</span></span>  
  
|<span data-ttu-id="2e4e8-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e4e8-115">HRESULT</span></span>|<span data-ttu-id="2e4e8-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e4e8-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2e4e8-117">`EnumFieldsWithName`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2e4e8-118">No hay ningún campo para enumerar.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-118">There are no fields to enumerate.</span></span> <span data-ttu-id="2e4e8-119">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="2e4e8-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e4e8-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e4e8-120">Requirements</span></span>  
 <span data-ttu-id="2e4e8-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e4e8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e4e8-122">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e4e8-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e4e8-123">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e4e8-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e4e8-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e4e8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e4e8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e4e8-125">See Also</span></span>  
 [<span data-ttu-id="2e4e8-126">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e4e8-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2e4e8-127">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e4e8-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
