---
title: "IMetaDataImport::EnumTypeDefs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeDefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a07d9ff237e6d3838fffb068e3a9ebf9febf66fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="0a559-102">IMetaDataImport::EnumTypeDefs (Método)</span><span class="sxs-lookup"><span data-stu-id="0a559-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="0a559-103">Enumera los tokens de TypeDef que representan todos los tipos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="0a559-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a559-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a559-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a559-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a559-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0a559-106">[out] Un puntero al nuevo enumerador.</span><span class="sxs-lookup"><span data-stu-id="0a559-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="0a559-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="0a559-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="0a559-108">[in] Matriz utilizada para almacenar los tokens de TypeDef.</span><span class="sxs-lookup"><span data-stu-id="0a559-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0a559-109">[in] Tamaño máximo de la matriz `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="0a559-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="0a559-110">[out] El número de tokens de TypeDef devueltos en `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="0a559-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a559-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0a559-111">Return Value</span></span>  
  
|<span data-ttu-id="0a559-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a559-112">HRESULT</span></span>|<span data-ttu-id="0a559-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0a559-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0a559-114">`EnumTypeDefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0a559-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0a559-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="0a559-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="0a559-116">En ese caso, `pcTypeDefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="0a559-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a559-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a559-117">Remarks</span></span>  
 <span data-ttu-id="0a559-118">El token de TypeDef representa un tipo como una clase o una interfaz, así como cualquier tipo de agregado a través de un mecanismo de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="0a559-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a559-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a559-119">Requirements</span></span>  
 <span data-ttu-id="0a559-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a559-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a559-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a559-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a559-122">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a559-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a559-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a559-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a559-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a559-124">See Also</span></span>  
 [<span data-ttu-id="0a559-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a559-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="0a559-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a559-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
