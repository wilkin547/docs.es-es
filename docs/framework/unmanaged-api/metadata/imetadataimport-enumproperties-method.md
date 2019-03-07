---
title: IMetaDataImport::EnumProperties (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b42c558009c25adfd7d282da905e7182dfd3342
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467030"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="2a03b-102">IMetaDataImport::EnumProperties (Método)</span><span class="sxs-lookup"><span data-stu-id="2a03b-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="2a03b-103">Enumera los tokens de PropertyDef que representan las propiedades del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="2a03b-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a03b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a03b-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a03b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a03b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2a03b-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="2a03b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2a03b-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="2a03b-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="2a03b-108">[in] Un token de TypeDef que representa el tipo con propiedades a enumerar.</span><span class="sxs-lookup"><span data-stu-id="2a03b-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="2a03b-109">[out] Matriz utilizada para almacenar los tokens de PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="2a03b-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2a03b-110">[in] Tamaño máximo de la matriz `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="2a03b-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="2a03b-111">[out] El número de tokens de PropertyDef devueltos en `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="2a03b-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a03b-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2a03b-112">Return Value</span></span>  
  
|<span data-ttu-id="2a03b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a03b-113">HRESULT</span></span>|<span data-ttu-id="2a03b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a03b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2a03b-115">`EnumProperties` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2a03b-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2a03b-116">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="2a03b-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="2a03b-117">En ese caso, `pcProperties` es cero.</span><span class="sxs-lookup"><span data-stu-id="2a03b-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a03b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a03b-118">Requirements</span></span>  
 <span data-ttu-id="2a03b-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a03b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a03b-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a03b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a03b-121">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a03b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a03b-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a03b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a03b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a03b-123">See also</span></span>
- [<span data-ttu-id="2a03b-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a03b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2a03b-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a03b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
