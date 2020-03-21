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
ms.openlocfilehash: fd7f149e806727d849cdceb3ffbc5dc7392fcf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177406"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="28788-102">IMetaDataEmit2::SetGenericParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="28788-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="28788-103">Establece los valores de propiedad para la definición de parámetro genérico a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="28788-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28788-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28788-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28788-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28788-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="28788-106">[en] El token para la definición de parámetro genérico para la que se establecen valores.</span><span class="sxs-lookup"><span data-stu-id="28788-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="28788-107">[en] Valor de la enumeración [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) que describe el tipo del parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="28788-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="28788-108">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="28788-108">[in] Optional.</span></span> <span data-ttu-id="28788-109">El nombre del parámetro para el que se establecen valores.</span><span class="sxs-lookup"><span data-stu-id="28788-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="28788-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="28788-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="28788-111">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="28788-111">[in] Optional.</span></span> <span data-ttu-id="28788-112">Matriz de tipos terminada en cero.</span><span class="sxs-lookup"><span data-stu-id="28788-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="28788-113">Los miembros `mdTypeDef`de `mdTypeRef`la `mdTypeSpec` matriz deben ser un token de metadatos , , o .</span><span class="sxs-lookup"><span data-stu-id="28788-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28788-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28788-114">Requirements</span></span>  
 <span data-ttu-id="28788-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28788-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28788-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="28788-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28788-117">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28788-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28788-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28788-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28788-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28788-119">See also</span></span>

- [<span data-ttu-id="28788-120">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28788-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="28788-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28788-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
