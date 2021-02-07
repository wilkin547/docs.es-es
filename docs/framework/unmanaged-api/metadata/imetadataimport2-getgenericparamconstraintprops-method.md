---
description: 'Más información sobre: IMetaDataImport2:: Getgenericparamconstraintprops ((método)'
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
ms.openlocfilehash: 03cc4df655f9ab7a1c04840e9d4fa782a90ce1ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688746"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="e0503-103">IMetaDataImport2::GetGenericParamConstraintProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e0503-103">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>

<span data-ttu-id="e0503-104">Obtiene los metadatos asociados a la restricción de parámetro genérico que representa el token de restricción especificado.</span><span class="sxs-lookup"><span data-stu-id="e0503-104">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0503-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0503-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0503-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0503-106">Parameters</span></span>  

 `gpc`  
 <span data-ttu-id="e0503-107">de Token de la restricción de parámetro genérico para el que se van a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="e0503-107">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="e0503-108">enuncia Puntero al token que representa el parámetro genérico que está restringido.</span><span class="sxs-lookup"><span data-stu-id="e0503-108">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="e0503-109">enuncia Un puntero a un token TypeDef, TypeRef o TypeSpec que representa una restricción en `ptGenericParam` .</span><span class="sxs-lookup"><span data-stu-id="e0503-109">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0503-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0503-110">Requirements</span></span>  

 <span data-ttu-id="e0503-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0503-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0503-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e0503-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0503-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0503-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0503-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0503-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0503-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0503-115">See also</span></span>

- [<span data-ttu-id="e0503-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0503-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="e0503-117">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0503-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
