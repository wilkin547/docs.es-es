---
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
ms.openlocfilehash: 8feba8e67f3a90dd48fd957065a9c166c204b87c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492748"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="7dee9-102">IMetaDataEmit2::SetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7dee9-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="7dee9-103">Establece los valores de propiedad para la definición de parámetro genérico a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="7dee9-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dee9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dee9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dee9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7dee9-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="7dee9-106">de Token de la definición de parámetro genérico para el que se van a establecer valores.</span><span class="sxs-lookup"><span data-stu-id="7dee9-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="7dee9-107">de Un valor de la enumeración [CorGenericParamAttr (](corgenericparamattr-enumeration.md) que describe el tipo para el parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="7dee9-107">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="7dee9-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="7dee9-108">[in] Optional.</span></span> <span data-ttu-id="7dee9-109">Nombre del parámetro para el que se van a establecer valores.</span><span class="sxs-lookup"><span data-stu-id="7dee9-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="7dee9-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="7dee9-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="7dee9-111">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="7dee9-111">[in] Optional.</span></span> <span data-ttu-id="7dee9-112">Matriz terminada en cero de restricciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="7dee9-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="7dee9-113">Los miembros de la matriz deben ser un `mdTypeDef` `mdTypeRef` `mdTypeSpec` token de metadatos, o.</span><span class="sxs-lookup"><span data-stu-id="7dee9-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dee9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7dee9-114">Requirements</span></span>  
 <span data-ttu-id="7dee9-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dee9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dee9-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7dee9-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7dee9-117">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7dee9-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7dee9-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dee9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dee9-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7dee9-119">See also</span></span>

- [<span data-ttu-id="7dee9-120">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7dee9-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="7dee9-121">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7dee9-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
