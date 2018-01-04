---
title: "IMetaDataImport::EnumTypeRefs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3099f129abd3477aeb08526b9f0dcd5b701d4dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="42616-102">IMetaDataImport::EnumTypeRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="42616-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="42616-103">Enumera los tokens de TypeRef definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="42616-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42616-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42616-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42616-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42616-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="42616-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="42616-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="42616-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="42616-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="42616-108">[out] Matriz utilizada para almacenar los tokens de TypeRef.</span><span class="sxs-lookup"><span data-stu-id="42616-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="42616-109">[in] Tamaño máximo de la matriz `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="42616-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="42616-110">[out] Un puntero al número de tokens de TypeRef que se devuelven en `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="42616-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42616-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42616-111">Return Value</span></span>  
  
|<span data-ttu-id="42616-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42616-112">HRESULT</span></span>|<span data-ttu-id="42616-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="42616-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="42616-114">`EnumTypeRefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="42616-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="42616-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="42616-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="42616-116">En ese caso, `pcTypeRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="42616-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42616-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42616-117">Remarks</span></span>  
 <span data-ttu-id="42616-118">Un token de TypeRef representa una referencia a un tipo.</span><span class="sxs-lookup"><span data-stu-id="42616-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42616-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42616-119">Requirements</span></span>  
 <span data-ttu-id="42616-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42616-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42616-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="42616-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42616-122">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42616-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42616-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42616-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42616-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="42616-124">See Also</span></span>  
 [<span data-ttu-id="42616-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42616-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="42616-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42616-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
