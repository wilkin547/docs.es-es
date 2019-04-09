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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d93c55cec3d35fd4208a4a8a7c9b235dd10fb9ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156174"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="0976f-102">IMetaDataEmit::DefineTypeRefByName (Método)</span><span class="sxs-lookup"><span data-stu-id="0976f-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="0976f-103">Obtiene los metadatos de un token para un tipo que se define en el ámbito especificado, que está fuera del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="0976f-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0976f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0976f-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0976f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0976f-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="0976f-106">[in] El token que especifica el ámbito de resolución.</span><span class="sxs-lookup"><span data-stu-id="0976f-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="0976f-107">Los siguientes tipos de token son válidos:</span><span class="sxs-lookup"><span data-stu-id="0976f-107">The following token types are valid:</span></span>  
  
-   `mdModuleRef`<span data-ttu-id="0976f-108">, si el tipo se define en el mismo ensamblado en el que se define el llamador.</span><span class="sxs-lookup"><span data-stu-id="0976f-108">, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
-   `mdAssemblyRef`<span data-ttu-id="0976f-109">, si el tipo está definido en un ensamblado distinto de aquél donde se define el autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="0976f-109">, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
-   `mdTypeRef`<span data-ttu-id="0976f-110">, si el tipo es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="0976f-110">, if the type is a nested type.</span></span>  
  
-   `mdModule`<span data-ttu-id="0976f-111">, si el tipo se define en el mismo módulo en el que se define el llamador.</span><span class="sxs-lookup"><span data-stu-id="0976f-111">, if the type is defined in the same module in which the caller is defined.</span></span>  
  
-   <span data-ttu-id="0976f-112">Es null, si el tipo está definido globalmente.</span><span class="sxs-lookup"><span data-stu-id="0976f-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="0976f-113">[in] El nombre del tipo de destino en Unicode.</span><span class="sxs-lookup"><span data-stu-id="0976f-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="0976f-114">[out] Un puntero a la `mdTypeRef` símbolo (token) que se asigna al tipo.</span><span class="sxs-lookup"><span data-stu-id="0976f-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0976f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0976f-115">Requirements</span></span>  
 <span data-ttu-id="0976f-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0976f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0976f-117">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="0976f-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0976f-118">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0976f-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0976f-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0976f-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0976f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0976f-120">See also</span></span>

- [<span data-ttu-id="0976f-121">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0976f-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0976f-122">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0976f-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
