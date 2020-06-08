---
title: IMetaDataImport2::GetGenericParamConstraintProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
ms.openlocfilehash: 8a1cdff313dae73e3f5e8918ff2ef395c80b115d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490633"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="22f7e-102">IMetaDataImport2::GetGenericParamConstraintProps (Método)</span><span class="sxs-lookup"><span data-stu-id="22f7e-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="22f7e-103">Obtiene los metadatos asociados a la restricción de parámetro genérico que representa el token de restricción especificado.</span><span class="sxs-lookup"><span data-stu-id="22f7e-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22f7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22f7e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22f7e-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="22f7e-106">de Token de la restricción de parámetro genérico para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="22f7e-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="22f7e-107">enuncia Puntero al token que representa el parámetro genérico que está restringido.</span><span class="sxs-lookup"><span data-stu-id="22f7e-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="22f7e-108">enuncia Un puntero a un token TypeDef, TypeRef o TypeSpec que representa una restricción en `ptGenericParam` .</span><span class="sxs-lookup"><span data-stu-id="22f7e-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22f7e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22f7e-109">Requirements</span></span>  
 <span data-ttu-id="22f7e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22f7e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22f7e-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="22f7e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22f7e-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="22f7e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22f7e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22f7e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f7e-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="22f7e-114">See also</span></span>

- [<span data-ttu-id="22f7e-115">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22f7e-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="22f7e-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22f7e-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
