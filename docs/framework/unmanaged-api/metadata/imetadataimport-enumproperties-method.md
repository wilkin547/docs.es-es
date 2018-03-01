---
title: "IMetaDataImport::EnumProperties (Método)"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 63ff10904440f55ec3fe6fb6aa581fbf560763e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="1e664-102">IMetaDataImport::EnumProperties (Método)</span><span class="sxs-lookup"><span data-stu-id="1e664-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="1e664-103">Enumera los tokens de PropertyDef que representan las propiedades del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="1e664-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e664-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e664-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e664-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e664-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1e664-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="1e664-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1e664-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="1e664-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="1e664-108">[in] Un token de TypeDef que representa el tipo con propiedades para enumerar.</span><span class="sxs-lookup"><span data-stu-id="1e664-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="1e664-109">[out] Matriz utilizada para almacenar los tokens de PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="1e664-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1e664-110">[in] Tamaño máximo de la matriz `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="1e664-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="1e664-111">[out] El número de tokens de PropertyDef devueltos en `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="1e664-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e664-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1e664-112">Return Value</span></span>  
  
|<span data-ttu-id="1e664-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e664-113">HRESULT</span></span>|<span data-ttu-id="1e664-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e664-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1e664-115">`EnumProperties`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e664-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1e664-116">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="1e664-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="1e664-117">En ese caso, `pcProperties` es cero.</span><span class="sxs-lookup"><span data-stu-id="1e664-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e664-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e664-118">Requirements</span></span>  
 <span data-ttu-id="1e664-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e664-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e664-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1e664-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e664-121">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e664-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e664-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e664-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e664-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e664-123">See Also</span></span>  
 [<span data-ttu-id="1e664-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e664-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1e664-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e664-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
