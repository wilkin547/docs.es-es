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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd8a2d373b801bd8238d50eecb388ef511bc34bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446207"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="d9f66-102">IMetaDataImport::EnumFields (Método)</span><span class="sxs-lookup"><span data-stu-id="d9f66-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="d9f66-103">Enumera los tokens de FieldDef del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="d9f66-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9f66-104">Syntax</span></span>  
  
```  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9f66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9f66-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d9f66-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="d9f66-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="d9f66-107">[in] El token de TypeDef de la clase cuyos campos se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="d9f66-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="d9f66-108">[out] La lista de tokens de FieldDef.</span><span class="sxs-lookup"><span data-stu-id="d9f66-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d9f66-109">[in] Tamaño máximo de la matriz `rFields`.</span><span class="sxs-lookup"><span data-stu-id="d9f66-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d9f66-110">[out] El número real de los tokens de FieldDef devueltos en `rFields`.</span><span class="sxs-lookup"><span data-stu-id="d9f66-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9f66-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9f66-111">Return Value</span></span>  
  
|<span data-ttu-id="d9f66-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9f66-112">HRESULT</span></span>|<span data-ttu-id="d9f66-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9f66-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d9f66-114">`EnumFields` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d9f66-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d9f66-115">No hay ningún campo para enumerar.</span><span class="sxs-lookup"><span data-stu-id="d9f66-115">There are no fields to enumerate.</span></span> <span data-ttu-id="d9f66-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="d9f66-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9f66-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9f66-117">Requirements</span></span>  
 <span data-ttu-id="d9f66-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9f66-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9f66-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9f66-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9f66-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9f66-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9f66-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9f66-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f66-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9f66-122">See Also</span></span>  
 [<span data-ttu-id="d9f66-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9f66-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d9f66-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9f66-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
