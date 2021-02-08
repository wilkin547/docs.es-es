---
description: 'Más información sobre: IMetaDataEmit2:: Setgenericparamprops ((método)'
title: IMetaDataEmit2::SetGenericParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 9c6946bbd301450203bc6fb2b1202352119dc792
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771657"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="85c11-103">IMetaDataEmit2::SetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="85c11-103">IMetaDataEmit2::SetGenericParamProps Method</span></span>

<span data-ttu-id="85c11-104">Establece los valores de propiedad para la definición de parámetro genérico a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="85c11-104">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c11-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85c11-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85c11-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85c11-106">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="85c11-107">de Token de la definición de parámetro genérico para el que se van a establecer valores.</span><span class="sxs-lookup"><span data-stu-id="85c11-107">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="85c11-108">de Un valor de la enumeración [CorGenericParamAttr (](corgenericparamattr-enumeration.md) que describe el tipo para el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="85c11-108">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="85c11-109">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="85c11-109">[in] Optional.</span></span> <span data-ttu-id="85c11-110">Nombre del parámetro para el que se van a establecer valores.</span><span class="sxs-lookup"><span data-stu-id="85c11-110">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="85c11-111">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="85c11-111">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="85c11-112">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="85c11-112">[in] Optional.</span></span> <span data-ttu-id="85c11-113">Matriz terminada en cero de restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="85c11-113">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="85c11-114">Los miembros de la matriz deben ser un `mdTypeDef` `mdTypeRef` `mdTypeSpec` token de metadatos, o.</span><span class="sxs-lookup"><span data-stu-id="85c11-114">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c11-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85c11-115">Requirements</span></span>  

 <span data-ttu-id="85c11-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85c11-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85c11-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="85c11-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85c11-118">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85c11-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85c11-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85c11-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c11-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="85c11-120">See also</span></span>

- [<span data-ttu-id="85c11-121">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85c11-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="85c11-122">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85c11-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
