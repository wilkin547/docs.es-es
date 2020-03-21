---
title: IMetaDataEmit::DefineTypeRefByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeRefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeRefByName
helpviewer_keywords:
- DefineTypeRefByName method [.NET Framework metadata]
- IMetaDataEmit::DefineTypeRefByName method [.NET Framework metadata]
ms.assetid: c30a4ce3-2d3e-411a-98df-e62ac4a5dd50
topic_type:
- apiref
ms.openlocfilehash: 23a6931b31ea2d7e4e8d1cb3dc8adf3a51216315
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175751"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="125e7-102">IMetaDataEmit::DefineTypeRefByName (Método)</span><span class="sxs-lookup"><span data-stu-id="125e7-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="125e7-103">Obtiene un token de metadatos para un tipo que se define en el ámbito especificado, que está fuera del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="125e7-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="125e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="125e7-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (
    [in]  mdToken     tkResolutionScope,
    [in]  LPCWSTR     szName,
    [out] mdTypeRef   *ptr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="125e7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="125e7-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="125e7-106">[en] El token que especifica el ámbito de resolución.</span><span class="sxs-lookup"><span data-stu-id="125e7-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="125e7-107">Los siguientes tipos de token son válidos:</span><span class="sxs-lookup"><span data-stu-id="125e7-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="125e7-108">`mdModuleRef`, si el tipo se define en el mismo ensamblado en el que se define el llamador.</span><span class="sxs-lookup"><span data-stu-id="125e7-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="125e7-109">`mdAssemblyRef`, si el tipo se define en un ensamblado distinto del que se define el llamador.</span><span class="sxs-lookup"><span data-stu-id="125e7-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="125e7-110">`mdTypeRef`, si el tipo es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="125e7-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="125e7-111">`mdModule`, si el tipo se define en el mismo módulo en el que se define el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="125e7-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="125e7-112">Null, si el tipo se define globalmente.</span><span class="sxs-lookup"><span data-stu-id="125e7-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="125e7-113">[en] El nombre del tipo de destino en Unicode.</span><span class="sxs-lookup"><span data-stu-id="125e7-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="125e7-114">[fuera] Puntero al `mdTypeRef` token asignado al tipo.</span><span class="sxs-lookup"><span data-stu-id="125e7-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="125e7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="125e7-115">Requirements</span></span>  
 <span data-ttu-id="125e7-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="125e7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="125e7-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="125e7-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="125e7-118">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="125e7-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="125e7-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="125e7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125e7-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="125e7-120">See also</span></span>

- [<span data-ttu-id="125e7-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="125e7-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="125e7-122">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="125e7-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
