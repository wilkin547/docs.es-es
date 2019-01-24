---
title: IMetaDataImport2::EnumMethodSpecs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4d660deb69e694a70a140b6d00c355442e3c5094
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558912"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="b9ee5-102">IMetaDataImport2::EnumMethodSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="b9ee5-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="b9ee5-103">Obtiene un enumerador para una matriz de símbolos (tokens) de MethodSpec asociada al MethodDef o MemberRef especificado (token).</span><span class="sxs-lookup"><span data-stu-id="b9ee5-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ee5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9ee5-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9ee5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9ee5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b9ee5-106">[in, out] Un puntero al enumerador para `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="b9ee5-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="b9ee5-107">[in] El token MemberRef o MethodDef que representa el método cuyos símbolos (tokens) MethodSpec se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="b9ee5-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="b9ee5-108">Si el valor de `tk` es 0 (cero), se enumerarán todos los tokens de MethodSpec en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="b9ee5-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="b9ee5-109">[out] Matriz de tokens MethodSpec a enumerar.</span><span class="sxs-lookup"><span data-stu-id="b9ee5-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b9ee5-110">[in] El número máximo solicitado de tokens para colocar en `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="b9ee5-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="b9ee5-111">[out] El número de símbolos (token) devuelto se coloca en `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="b9ee5-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9ee5-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9ee5-112">Return Value</span></span>  
  
|<span data-ttu-id="b9ee5-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9ee5-113">HRESULT</span></span>|<span data-ttu-id="b9ee5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9ee5-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b9ee5-115">`EnumMethodSpecs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b9ee5-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b9ee5-116">`phEnum` no tiene ningún elemento de miembro.</span><span class="sxs-lookup"><span data-stu-id="b9ee5-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="b9ee5-117">En este caso, `pcMethodSpecs` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="b9ee5-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9ee5-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9ee5-118">Requirements</span></span>  
 <span data-ttu-id="b9ee5-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9ee5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ee5-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b9ee5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9ee5-121">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9ee5-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9ee5-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ee5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ee5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9ee5-123">See also</span></span>
- [<span data-ttu-id="b9ee5-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9ee5-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="b9ee5-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9ee5-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
