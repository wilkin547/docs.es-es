---
description: 'Más información sobre: IMetaDataImport:: EnumFieldsWithName ((método)'
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
ms.openlocfilehash: 88096b2b12a9571eb05d4550e6e26a348e28cfd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799375"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="e28e3-103">IMetaDataImport::EnumFieldsWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="e28e3-103">IMetaDataImport::EnumFieldsWithName Method</span></span>

<span data-ttu-id="e28e3-104">Enumera los tokens de FieldDef del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="e28e3-104">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e28e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e28e3-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e28e3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e28e3-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e28e3-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="e28e3-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="e28e3-108">de Token del tipo cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="e28e3-108">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="e28e3-109">de Nombre del campo que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="e28e3-109">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="e28e3-110">enuncia Matriz que se usa para almacenar los tokens de FieldDef.</span><span class="sxs-lookup"><span data-stu-id="e28e3-110">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e28e3-111">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="e28e3-111">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e28e3-112">enuncia Número real de tokens de FieldDef devueltos en `rFields` .</span><span class="sxs-lookup"><span data-stu-id="e28e3-112">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e28e3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e28e3-113">Remarks</span></span>  

 <span data-ttu-id="e28e3-114">A diferencia de [IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` descarta todos los tokens de campo que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="e28e3-114">Unlike [IMetaDataImport::EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e28e3-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e28e3-115">Return Value</span></span>  
  
|<span data-ttu-id="e28e3-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e28e3-116">HRESULT</span></span>|<span data-ttu-id="e28e3-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e28e3-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e28e3-118">`EnumFieldsWithName` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e28e3-118">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e28e3-119">No hay campos que enumerar.</span><span class="sxs-lookup"><span data-stu-id="e28e3-119">There are no fields to enumerate.</span></span> <span data-ttu-id="e28e3-120">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="e28e3-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e28e3-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e28e3-121">Requirements</span></span>  

 <span data-ttu-id="e28e3-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e28e3-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e28e3-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e28e3-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e28e3-124">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e28e3-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e28e3-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e28e3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28e3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e28e3-126">See also</span></span>

- [<span data-ttu-id="e28e3-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e28e3-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e28e3-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e28e3-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
