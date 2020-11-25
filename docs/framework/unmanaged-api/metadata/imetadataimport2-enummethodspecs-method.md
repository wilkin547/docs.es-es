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
ms.openlocfilehash: 26b345567699c5780827ed835cff13069ea8f609
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702750"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="deb3f-102">IMetaDataImport2::EnumMethodSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="deb3f-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>

<span data-ttu-id="deb3f-103">Obtiene un enumerador para una matriz de tokens MethodSpec asociados al token MethodDef o MemberRef especificado.</span><span class="sxs-lookup"><span data-stu-id="deb3f-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="deb3f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="deb3f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="deb3f-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="deb3f-106">[in, out] Puntero al enumerador de `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="deb3f-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="deb3f-107">de El token MemberRef o MethodDef que representa el método cuyos tokens MethodSpec se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="deb3f-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="deb3f-108">Si el valor de `tk` es 0 (cero), se enumerarán todos los tokens MethodSpec en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="deb3f-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="deb3f-109">enuncia Matriz de tokens MethodSpec que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="deb3f-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="deb3f-110">de Número máximo solicitado de tokens que se van a colocar en `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="deb3f-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="deb3f-111">enuncia Número devuelto de tokens colocados en `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="deb3f-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="deb3f-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="deb3f-112">Return Value</span></span>  
  
|<span data-ttu-id="deb3f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="deb3f-113">HRESULT</span></span>|<span data-ttu-id="deb3f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="deb3f-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="deb3f-115">`EnumMethodSpecs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="deb3f-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="deb3f-116">`phEnum` no tiene elementos de miembro.</span><span class="sxs-lookup"><span data-stu-id="deb3f-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="deb3f-117">En este caso, `pcMethodSpecs` se establece en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="deb3f-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="deb3f-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="deb3f-118">Requirements</span></span>  

 <span data-ttu-id="deb3f-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deb3f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb3f-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="deb3f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="deb3f-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="deb3f-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="deb3f-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb3f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb3f-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="deb3f-123">See also</span></span>

- [<span data-ttu-id="deb3f-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="deb3f-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="deb3f-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="deb3f-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
