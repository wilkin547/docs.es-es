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
ms.openlocfilehash: e4401ea8a70e7ace8d8efc5e0a6d29f6db51b3df
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503820"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="58b19-102">IMetaDataEmit2::DefineGenericParam (Método)</span><span class="sxs-lookup"><span data-stu-id="58b19-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="58b19-103">Crea una definición para un parámetro de tipo genérico y obtiene un token para ese parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="58b19-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b19-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58b19-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="58b19-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58b19-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="58b19-106">de Un `mdTypeDef` `mdMethodDef` token o que representa el método o constructor para el que se va a definir un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="58b19-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="58b19-107">de Índice del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="58b19-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="58b19-108">de Un valor de la enumeración [CorGenericParamAttr (](corgenericparamattr-enumeration.md) que describe el tipo para el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="58b19-108">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="58b19-109">de Nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="58b19-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="58b19-110">de Este parámetro está reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="58b19-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="58b19-111">de Matriz terminada en cero de restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="58b19-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="58b19-112">Los miembros de la matriz deben ser un `mdTypeDef` `mdTypeRef` `mdTypeSpec` token de metadatos, o.</span><span class="sxs-lookup"><span data-stu-id="58b19-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="58b19-113">enuncia Token que representa el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="58b19-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58b19-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58b19-114">Requirements</span></span>  
 <span data-ttu-id="58b19-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58b19-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b19-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="58b19-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58b19-117">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="58b19-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58b19-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b19-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b19-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="58b19-119">See also</span></span>

- [<span data-ttu-id="58b19-120">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="58b19-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="58b19-121">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="58b19-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
