---
title: "IMetaDataImport::EnumCustomAttributes (Método)"
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
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e45c15f3d09972d1c83c9b330965c4e8afd21b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="dab01-102">IMetaDataImport::EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="dab01-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="dab01-103">Enumera los tokens de definición de atributos personalizados asociados con el tipo o miembro especificado.</span><span class="sxs-lookup"><span data-stu-id="dab01-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dab01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dab01-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dab01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dab01-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="dab01-106">[entrada, salida] Un puntero al enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="dab01-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="dab01-107">[in] Un token para el ámbito de la enumeración, o cero para todos los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="dab01-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="dab01-108">[in] Un token para el constructor del tipo de los atributos que se van a enumerar, o `null` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="dab01-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="dab01-109">[out] Una matriz de símbolos (tokens) de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="dab01-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dab01-110">[in] Tamaño máximo de la matriz `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="dab01-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="dab01-111">[out, optional] El número real de valores de símbolo (token) devueltos por `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="dab01-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dab01-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dab01-112">Return Value</span></span>  
  
|<span data-ttu-id="dab01-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dab01-113">HRESULT</span></span>|<span data-ttu-id="dab01-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="dab01-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="dab01-115">`EnumCustomAttributes`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dab01-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="dab01-116">No hay ningún atributo personalizado para enumerar.</span><span class="sxs-lookup"><span data-stu-id="dab01-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="dab01-117">En ese caso, `pcCustomAttributes` es cero.</span><span class="sxs-lookup"><span data-stu-id="dab01-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dab01-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dab01-118">Requirements</span></span>  
 <span data-ttu-id="dab01-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dab01-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dab01-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dab01-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dab01-121">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dab01-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dab01-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dab01-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab01-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dab01-123">See Also</span></span>  
 [<span data-ttu-id="dab01-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dab01-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="dab01-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dab01-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
