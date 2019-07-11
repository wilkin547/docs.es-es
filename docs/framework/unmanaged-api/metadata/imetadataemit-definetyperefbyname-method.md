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
ms.openlocfilehash: f005ee9d3d9d4b8977cd6a1838fe46015e604df5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777470"
---
# <a name="imetadataemitdefinetyperefbyname-method"></a><span data-ttu-id="f7d4a-102">IMetaDataEmit::DefineTypeRefByName (Método)</span><span class="sxs-lookup"><span data-stu-id="f7d4a-102">IMetaDataEmit::DefineTypeRefByName Method</span></span>
<span data-ttu-id="f7d4a-103">Obtiene los metadatos de un token para un tipo que se define en el ámbito especificado, que está fuera del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-103">Gets a metadata token for a type that is defined in the specified scope, which is outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d4a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7d4a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeRefByName (   
    [in]  mdToken     tkResolutionScope,   
    [in]  LPCWSTR     szName,   
    [out] mdTypeRef   *ptr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7d4a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7d4a-105">Parameters</span></span>  
 `tkResolutionScope`  
 <span data-ttu-id="f7d4a-106">[in] El token que especifica el ámbito de resolución.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-106">[in] The token specifying the resolution scope.</span></span> <span data-ttu-id="f7d4a-107">Los siguientes tipos de token son válidos:</span><span class="sxs-lookup"><span data-stu-id="f7d4a-107">The following token types are valid:</span></span>  
  
- <span data-ttu-id="f7d4a-108">`mdModuleRef`, si el tipo se define en el mismo ensamblado en el que se define el llamador.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-108">`mdModuleRef`, if the type is defined in the same assembly in which the caller is defined.</span></span>  
  
- <span data-ttu-id="f7d4a-109">`mdAssemblyRef`, si el tipo está definido en un ensamblado distinto de aquél donde se define el autor de llamada.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-109">`mdAssemblyRef`, if the type is defined in an assembly other than the one in which the caller is defined.</span></span>  
  
- <span data-ttu-id="f7d4a-110">`mdTypeRef`, si el tipo es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-110">`mdTypeRef`, if the type is a nested type.</span></span>  
  
- <span data-ttu-id="f7d4a-111">`mdModule`, si el tipo se define en el mismo módulo en el que se define el llamador.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-111">`mdModule`, if the type is defined in the same module in which the caller is defined.</span></span>  
  
- <span data-ttu-id="f7d4a-112">Es null, si el tipo está definido globalmente.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-112">Null, if the type is defined globally.</span></span>  
  
 `szName`  
 <span data-ttu-id="f7d4a-113">[in] El nombre del tipo de destino en Unicode.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-113">[in] The name of the target type in Unicode.</span></span>  
  
 `ptr`  
 <span data-ttu-id="f7d4a-114">[out] Un puntero a la `mdTypeRef` símbolo (token) que se asigna al tipo.</span><span class="sxs-lookup"><span data-stu-id="f7d4a-114">[out] A pointer to the `mdTypeRef` token that is assigned to the type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d4a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7d4a-115">Requirements</span></span>  
 <span data-ttu-id="f7d4a-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7d4a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7d4a-117">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f7d4a-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7d4a-118">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f7d4a-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7d4a-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7d4a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d4a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7d4a-120">See also</span></span>

- [<span data-ttu-id="f7d4a-121">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7d4a-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f7d4a-122">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7d4a-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
