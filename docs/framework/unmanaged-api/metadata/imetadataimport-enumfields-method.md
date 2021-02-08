---
description: 'Más información acerca de: IMetaDataImport:: EnumFields (método)'
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
ms.openlocfilehash: 5cb9b3a47dc4c51b9eba24b9519e4b97846c1a6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799387"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="1255d-103">IMetaDataImport::EnumFields (Método)</span><span class="sxs-lookup"><span data-stu-id="1255d-103">IMetaDataImport::EnumFields Method</span></span>

<span data-ttu-id="1255d-104">Enumera los tokens de FieldDef del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="1255d-104">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1255d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1255d-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1255d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1255d-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="1255d-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="1255d-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="1255d-108">de El token TypeDef de la clase cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="1255d-108">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="1255d-109">enuncia Lista de tokens de FieldDef.</span><span class="sxs-lookup"><span data-stu-id="1255d-109">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1255d-110">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="1255d-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1255d-111">enuncia Número real de tokens de FieldDef devueltos en `rFields` .</span><span class="sxs-lookup"><span data-stu-id="1255d-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1255d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1255d-112">Return Value</span></span>  
  
|<span data-ttu-id="1255d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1255d-113">HRESULT</span></span>|<span data-ttu-id="1255d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1255d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1255d-115">`EnumFields` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1255d-115">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1255d-116">No hay campos que enumerar.</span><span class="sxs-lookup"><span data-stu-id="1255d-116">There are no fields to enumerate.</span></span> <span data-ttu-id="1255d-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="1255d-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1255d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1255d-118">Requirements</span></span>  

 <span data-ttu-id="1255d-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1255d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1255d-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1255d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1255d-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1255d-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1255d-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1255d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1255d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1255d-123">See also</span></span>

- [<span data-ttu-id="1255d-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1255d-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1255d-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1255d-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
