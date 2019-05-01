---
title: IMetaDataImport::EnumFieldsWithName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf624695136a9397937f05b28dec18493c8e12d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042710"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="c9f8f-102">IMetaDataImport::EnumFieldsWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="c9f8f-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="c9f8f-103">Enumera los tokens de FieldDef del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9f8f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9f8f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c9f8f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9f8f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c9f8f-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="c9f8f-107">[in] El token del tipo cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="c9f8f-108">[in] El nombre del campo que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="c9f8f-109">[out] Matriz utilizada para almacenar los tokens de FieldDef.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c9f8f-110">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c9f8f-111">[out] El número real de los tokens de FieldDef devueltos en `rFields`.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9f8f-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9f8f-112">Remarks</span></span>  
 <span data-ttu-id="c9f8f-113">A diferencia de [EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` descarta todos los tokens de campo que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9f8f-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c9f8f-114">Return Value</span></span>  
  
|<span data-ttu-id="c9f8f-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9f8f-115">HRESULT</span></span>|<span data-ttu-id="c9f8f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9f8f-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c9f8f-117">`EnumFieldsWithName` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c9f8f-118">No hay ningún campo para enumerar.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-118">There are no fields to enumerate.</span></span> <span data-ttu-id="c9f8f-119">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="c9f8f-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9f8f-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9f8f-120">Requirements</span></span>  
 <span data-ttu-id="c9f8f-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9f8f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9f8f-122">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c9f8f-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9f8f-123">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9f8f-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c9f8f-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9f8f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f8f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9f8f-125">See also</span></span>

- [<span data-ttu-id="c9f8f-126">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9f8f-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c9f8f-127">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9f8f-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
