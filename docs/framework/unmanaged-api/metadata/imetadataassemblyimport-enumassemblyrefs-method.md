---
title: IMetaDataAssemblyImport::EnumAssemblyRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: 6a4489d094974eb872b39824ceb185b0cbe48625
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177827"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="b2d8b-102">IMetaDataAssemblyImport::EnumAssemblyRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="b2d8b-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="b2d8b-103">Enumera las `mdAssemblyRef` instancias que se definen en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b2d8b-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2d8b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2d8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2d8b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b2d8b-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="b2d8b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b2d8b-107">Debe ser un valor `EnumAssemblyRefs` nulo cuando se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="b2d8b-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="b2d8b-108">[fuera] La enumeración de tokens de `mdAssemblyRef` metadatos.</span><span class="sxs-lookup"><span data-stu-id="b2d8b-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b2d8b-109">[en] El número máximo de tokens que `rAssemblyRefs` se pueden colocar en la matriz.</span><span class="sxs-lookup"><span data-stu-id="b2d8b-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b2d8b-110">[fuera] El número de tokens `rAssemblyRefs`colocados en .</span><span class="sxs-lookup"><span data-stu-id="b2d8b-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2d8b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2d8b-111">Return Value</span></span>  
  
|<span data-ttu-id="b2d8b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2d8b-112">HRESULT</span></span>|<span data-ttu-id="b2d8b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2d8b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b2d8b-114">`EnumAssemblyRefs`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="b2d8b-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b2d8b-115">No hay tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="b2d8b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b2d8b-116">En este `pcTokens` caso, se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="b2d8b-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2d8b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2d8b-117">Requirements</span></span>  
 <span data-ttu-id="b2d8b-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2d8b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2d8b-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b2d8b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2d8b-120">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2d8b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2d8b-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2d8b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d8b-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2d8b-122">See also</span></span>

- [<span data-ttu-id="b2d8b-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2d8b-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
