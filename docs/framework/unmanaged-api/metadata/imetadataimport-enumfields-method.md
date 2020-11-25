---
title: IMetaDataImport::EnumFields (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 74035e9551cb1d622b326e511c3884e1eadf057f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711603"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="e31c5-102">IMetaDataImport::EnumFields (Método)</span><span class="sxs-lookup"><span data-stu-id="e31c5-102">IMetaDataImport::EnumFields Method</span></span>

<span data-ttu-id="e31c5-103">Enumera los tokens de FieldDef del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="e31c5-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e31c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e31c5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e31c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e31c5-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="e31c5-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="e31c5-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="e31c5-107">de El token TypeDef de la clase cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="e31c5-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="e31c5-108">enuncia Lista de tokens de FieldDef.</span><span class="sxs-lookup"><span data-stu-id="e31c5-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e31c5-109">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="e31c5-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e31c5-110">enuncia Número real de tokens de FieldDef devueltos en `rFields` .</span><span class="sxs-lookup"><span data-stu-id="e31c5-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e31c5-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e31c5-111">Return Value</span></span>  
  
|<span data-ttu-id="e31c5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e31c5-112">HRESULT</span></span>|<span data-ttu-id="e31c5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e31c5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e31c5-114">`EnumFields` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e31c5-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e31c5-115">No hay campos que enumerar.</span><span class="sxs-lookup"><span data-stu-id="e31c5-115">There are no fields to enumerate.</span></span> <span data-ttu-id="e31c5-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="e31c5-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e31c5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e31c5-117">Requirements</span></span>  

 <span data-ttu-id="e31c5-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e31c5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e31c5-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e31c5-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e31c5-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e31c5-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e31c5-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e31c5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e31c5-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e31c5-122">See also</span></span>

- [<span data-ttu-id="e31c5-123">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e31c5-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e31c5-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e31c5-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
