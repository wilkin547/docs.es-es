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
ms.openlocfilehash: 0a254587282dea43a3507fbbeca35bd7aa9604f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711577"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="4e91e-102">IMetaDataImport::EnumFieldsWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="4e91e-102">IMetaDataImport::EnumFieldsWithName Method</span></span>

<span data-ttu-id="4e91e-103">Enumera los tokens de FieldDef del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="4e91e-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e91e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e91e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4e91e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e91e-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="4e91e-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="4e91e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="4e91e-107">de Token del tipo cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="4e91e-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e91e-108">de Nombre del campo que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="4e91e-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="4e91e-109">enuncia Matriz que se usa para almacenar los tokens de FieldDef.</span><span class="sxs-lookup"><span data-stu-id="4e91e-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4e91e-110">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="4e91e-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4e91e-111">enuncia Número real de tokens de FieldDef devueltos en `rFields` .</span><span class="sxs-lookup"><span data-stu-id="4e91e-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e91e-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e91e-112">Remarks</span></span>  

 <span data-ttu-id="4e91e-113">A diferencia de [IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` descarta todos los tokens de campo que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="4e91e-113">Unlike [IMetaDataImport::EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e91e-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e91e-114">Return Value</span></span>  
  
|<span data-ttu-id="4e91e-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e91e-115">HRESULT</span></span>|<span data-ttu-id="4e91e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e91e-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4e91e-117">`EnumFieldsWithName` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e91e-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4e91e-118">No hay campos que enumerar.</span><span class="sxs-lookup"><span data-stu-id="4e91e-118">There are no fields to enumerate.</span></span> <span data-ttu-id="4e91e-119">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="4e91e-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e91e-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e91e-120">Requirements</span></span>  

 <span data-ttu-id="4e91e-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e91e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e91e-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e91e-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e91e-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e91e-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e91e-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e91e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e91e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e91e-125">See also</span></span>

- [<span data-ttu-id="4e91e-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e91e-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4e91e-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e91e-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
