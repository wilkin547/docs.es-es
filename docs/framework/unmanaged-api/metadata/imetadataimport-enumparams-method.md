---
title: "IMetaDataImport::EnumParams (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42555e1300016222e9ea8064e90fa3062d79db6a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="80959-102">IMetaDataImport::EnumParams (Método)</span><span class="sxs-lookup"><span data-stu-id="80959-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="80959-103">Enumera los tokens de ParamDef que representan los parámetros del método al que hace referencia el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="80959-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80959-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80959-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80959-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80959-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="80959-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="80959-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="80959-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="80959-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="80959-108">[in] Símbolo (token) de MethodDef que representa el método con los parámetros para enumerar.</span><span class="sxs-lookup"><span data-stu-id="80959-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="80959-109">[out] Matriz utilizada para almacenar los tokens de ParamDef.</span><span class="sxs-lookup"><span data-stu-id="80959-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="80959-110">[in] Tamaño máximo de la matriz `rParams`.</span><span class="sxs-lookup"><span data-stu-id="80959-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="80959-111">[out] El número de símbolos (tokens) de ParamDef devueltos en `rParams`.</span><span class="sxs-lookup"><span data-stu-id="80959-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80959-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80959-112">Return Value</span></span>  
  
|<span data-ttu-id="80959-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80959-113">HRESULT</span></span>|<span data-ttu-id="80959-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="80959-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="80959-115">`EnumParams`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="80959-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="80959-116">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="80959-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="80959-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="80959-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80959-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80959-118">Requirements</span></span>  
 <span data-ttu-id="80959-119">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80959-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80959-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="80959-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80959-121">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80959-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80959-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80959-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80959-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="80959-123">See Also</span></span>  
 [<span data-ttu-id="80959-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80959-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="80959-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80959-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
