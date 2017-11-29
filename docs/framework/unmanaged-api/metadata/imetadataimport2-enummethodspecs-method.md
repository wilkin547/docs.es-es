---
title: "IMetaDataImport2::EnumMethodSpecs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumMethodSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db1968c73d5a1c6e0687bc86f249c70b6c21712c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="0580b-102">IMetaDataImport2::EnumMethodSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="0580b-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="0580b-103">Obtiene un enumerador para una matriz de símbolos (tokens) de MethodSpec asociada al MethodDef o MemberRef especificado (token).</span><span class="sxs-lookup"><span data-stu-id="0580b-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0580b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0580b-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="0580b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0580b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0580b-106">[entrada, salida] Un puntero al enumerador para `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="0580b-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="0580b-107">[in] El token MemberRef o MethodDef que representa el método cuyos símbolos (tokens) MethodSpec se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="0580b-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="0580b-108">Si el valor de `tk` es 0 (cero), se enumerarán todos los tokens de MethodSpec en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="0580b-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="0580b-109">[out] Matriz de símbolos (tokens) de MethodSpec a enumerar.</span><span class="sxs-lookup"><span data-stu-id="0580b-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0580b-110">[in] El número máximo solicitado de símbolos (tokens) para colocar en `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="0580b-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="0580b-111">[out] El número devuelto de símbolos (tokens) se coloca en `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="0580b-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0580b-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0580b-112">Return Value</span></span>  
  
|<span data-ttu-id="0580b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0580b-113">HRESULT</span></span>|<span data-ttu-id="0580b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0580b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0580b-115">`EnumMethodSpecs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0580b-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0580b-116">`phEnum`no tiene ningún elemento de miembro.</span><span class="sxs-lookup"><span data-stu-id="0580b-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="0580b-117">En este caso, `pcMethodSpecs` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="0580b-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0580b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0580b-118">Requirements</span></span>  
 <span data-ttu-id="0580b-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0580b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0580b-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0580b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0580b-121">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0580b-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0580b-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0580b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0580b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0580b-123">See Also</span></span>  
 [<span data-ttu-id="0580b-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0580b-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="0580b-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0580b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
