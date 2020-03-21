---
title: IMetaDataEmit2::DefineGenericParam (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: 1868d13a9dbb73dbdf64e49c395bdbff02ce89d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177453"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="0fdd7-102">IMetaDataEmit2::DefineGenericParam (Método)</span><span class="sxs-lookup"><span data-stu-id="0fdd7-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="0fdd7-103">Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0fdd7-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fdd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fdd7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fdd7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fdd7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0fdd7-106">[en] Un `mdTypeDef` `mdMethodDef` token que representa el método o constructor para el que se va a definir un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="0fdd7-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="0fdd7-107">[en] El índice del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="0fdd7-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="0fdd7-108">[en] Valor de la enumeración [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) que describe el tipo del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="0fdd7-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="0fdd7-109">[en] El nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="0fdd7-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="0fdd7-110">[en] Este parámetro está reservado para la extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="0fdd7-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="0fdd7-111">[en] Matriz de tipos terminada en cero.</span><span class="sxs-lookup"><span data-stu-id="0fdd7-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="0fdd7-112">Los miembros `mdTypeDef`de `mdTypeRef`la `mdTypeSpec` matriz deben ser un token de metadatos , , o .</span><span class="sxs-lookup"><span data-stu-id="0fdd7-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="0fdd7-113">[fuera] Un token que representa el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="0fdd7-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fdd7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fdd7-114">Requirements</span></span>  
 <span data-ttu-id="0fdd7-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fdd7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fdd7-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0fdd7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0fdd7-117">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0fdd7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0fdd7-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fdd7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fdd7-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0fdd7-119">See also</span></span>

- [<span data-ttu-id="0fdd7-120">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fdd7-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="0fdd7-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fdd7-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
