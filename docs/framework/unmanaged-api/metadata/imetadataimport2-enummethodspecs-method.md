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
ms.openlocfilehash: 2df53ba53c64e042abc54a1d2ac043d301acdde9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177170"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="36511-102">IMetaDataImport2::EnumMethodSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="36511-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="36511-103">Obtiene un enumerador para una matriz de tokens MethodSpec asociados con el token MethodDef o MemberRef especificado.</span><span class="sxs-lookup"><span data-stu-id="36511-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36511-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36511-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="36511-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36511-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="36511-106">[adentro, fuera] Un puntero al `rMethodSpecs`enumerador para .</span><span class="sxs-lookup"><span data-stu-id="36511-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="36511-107">[en] El token MemberRef o MethodDef que representa el método cuyos tokens MethodSpec se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="36511-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="36511-108">Si el `tk` valor de es 0 (cero), se enumerarán todos los tokens MethodSpec del ámbito.</span><span class="sxs-lookup"><span data-stu-id="36511-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="36511-109">[fuera] Matriz de tokens MethodSpec que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="36511-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="36511-110">[en] El número máximo solicitado de `rMethodSpecs`tokens para colocar en .</span><span class="sxs-lookup"><span data-stu-id="36511-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="36511-111">[fuera] El número devuelto de `rMethodSpecs`tokens colocados en .</span><span class="sxs-lookup"><span data-stu-id="36511-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36511-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36511-112">Return Value</span></span>  
  
|<span data-ttu-id="36511-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36511-113">HRESULT</span></span>|<span data-ttu-id="36511-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="36511-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="36511-115">`EnumMethodSpecs`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="36511-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="36511-116">`phEnum`no tiene elementos miembro.</span><span class="sxs-lookup"><span data-stu-id="36511-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="36511-117">En este `pcMethodSpecs` caso, se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="36511-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="36511-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36511-118">Requirements</span></span>  
 <span data-ttu-id="36511-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36511-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36511-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36511-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36511-121">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36511-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36511-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36511-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36511-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36511-123">See also</span></span>

- [<span data-ttu-id="36511-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36511-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="36511-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36511-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
