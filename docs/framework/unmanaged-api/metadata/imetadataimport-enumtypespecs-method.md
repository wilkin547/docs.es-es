---
title: "IMetaDataImport::EnumTypeSpecs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a872af384a8df624178d8d37d5ad98a0b5c561d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="f75ce-102">IMetaDataImport::EnumTypeSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="f75ce-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="f75ce-103">Enumera los tokens de TypeSpec definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f75ce-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f75ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f75ce-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f75ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f75ce-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f75ce-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="f75ce-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f75ce-107">Este valor debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="f75ce-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="f75ce-108">[out] Matriz utilizada para almacenar los tokens de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="f75ce-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f75ce-109">[in] Tamaño máximo de la matriz `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="f75ce-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="f75ce-110">[out] El número de símbolos (tokens) de TypeSpec devueltos en `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="f75ce-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f75ce-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f75ce-111">Return Value</span></span>  
  
|<span data-ttu-id="f75ce-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f75ce-112">HRESULT</span></span>|<span data-ttu-id="f75ce-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f75ce-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f75ce-114">`EnumTypeSpecs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f75ce-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f75ce-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="f75ce-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f75ce-116">En ese caso, `pcTypeSpecs` es cero.</span><span class="sxs-lookup"><span data-stu-id="f75ce-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f75ce-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f75ce-117">Remarks</span></span>  
 <span data-ttu-id="f75ce-118">Los tokens de TypeSpec se crean mediante el [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f75ce-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f75ce-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f75ce-119">Requirements</span></span>  
 <span data-ttu-id="f75ce-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f75ce-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f75ce-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f75ce-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f75ce-122">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f75ce-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f75ce-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f75ce-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75ce-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f75ce-124">See Also</span></span>  
 [<span data-ttu-id="f75ce-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f75ce-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f75ce-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f75ce-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
