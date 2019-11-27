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
ms.openlocfilehash: 06b81615565a04db7d6cfef4da9b5372a85afd68
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450347"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="e6d61-102">IMetaDataAssemblyImport::EnumAssemblyRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="e6d61-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="e6d61-103">Enumera las instancias de `mdAssemblyRef` definidas en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e6d61-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6d61-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6d61-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6d61-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e6d61-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="e6d61-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e6d61-107">Debe ser un valor NULL cuando se llama al método `EnumAssemblyRefs` por primera vez.</span><span class="sxs-lookup"><span data-stu-id="e6d61-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="e6d61-108">enuncia Enumeración de los tokens de metadatos de `mdAssemblyRef`.</span><span class="sxs-lookup"><span data-stu-id="e6d61-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e6d61-109">de Número máximo de tokens que se pueden colocar en la matriz de `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="e6d61-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e6d61-110">enuncia Número de tokens realmente colocados en `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="e6d61-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6d61-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6d61-111">Return Value</span></span>  
  
|<span data-ttu-id="e6d61-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6d61-112">HRESULT</span></span>|<span data-ttu-id="e6d61-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6d61-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e6d61-114">`EnumAssemblyRefs` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6d61-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e6d61-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="e6d61-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e6d61-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="e6d61-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6d61-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6d61-117">Requirements</span></span>  
 <span data-ttu-id="e6d61-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6d61-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d61-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e6d61-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6d61-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e6d61-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e6d61-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d61-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d61-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6d61-122">See also</span></span>

- [<span data-ttu-id="e6d61-123">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6d61-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
