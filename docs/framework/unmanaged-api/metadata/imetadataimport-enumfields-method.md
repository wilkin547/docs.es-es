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
ms.openlocfilehash: be2845d1d660d86447cfbb6f2845a8e68b727e66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175517"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="57260-102">IMetaDataImport::EnumFields (Método)</span><span class="sxs-lookup"><span data-stu-id="57260-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="57260-103">Enumera los tokens de FieldDef del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="57260-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57260-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57260-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57260-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57260-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="57260-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="57260-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="57260-107">[en] El token TypeDef de la clase cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="57260-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="57260-108">[fuera] La lista de tokens FieldDef.</span><span class="sxs-lookup"><span data-stu-id="57260-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="57260-109">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="57260-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="57260-110">[fuera] El número real de tokens `rFields`FieldDef devueltos en .</span><span class="sxs-lookup"><span data-stu-id="57260-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57260-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="57260-111">Return Value</span></span>  
  
|<span data-ttu-id="57260-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57260-112">HRESULT</span></span>|<span data-ttu-id="57260-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="57260-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="57260-114">`EnumFields`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="57260-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="57260-115">No hay campos que enumerar.</span><span class="sxs-lookup"><span data-stu-id="57260-115">There are no fields to enumerate.</span></span> <span data-ttu-id="57260-116">En ese `pcTokens` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="57260-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57260-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57260-117">Requirements</span></span>  
 <span data-ttu-id="57260-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57260-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57260-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="57260-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57260-120">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57260-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57260-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57260-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57260-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57260-122">See also</span></span>

- [<span data-ttu-id="57260-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="57260-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="57260-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="57260-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
