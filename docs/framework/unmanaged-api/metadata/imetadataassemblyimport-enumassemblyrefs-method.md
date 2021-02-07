---
description: 'Más información sobre: IMetaDataAssemblyImport:: EnumAssemblyRefs ((método)'
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
ms.openlocfilehash: fc1d74d79edc21c6d3d13c80510440333d083801
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671066"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="a9c73-103">IMetaDataAssemblyImport::EnumAssemblyRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="a9c73-103">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>

<span data-ttu-id="a9c73-104">Enumera las `mdAssemblyRef` instancias de definidas en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a9c73-104">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c73-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9c73-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9c73-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9c73-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a9c73-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="a9c73-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a9c73-108">Debe ser un valor NULL cuando `EnumAssemblyRefs` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a9c73-108">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="a9c73-109">enuncia Enumeración de los `mdAssemblyRef` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="a9c73-109">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a9c73-110">de Número máximo de tokens que se pueden colocar en la `rAssemblyRefs` matriz.</span><span class="sxs-lookup"><span data-stu-id="a9c73-110">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a9c73-111">enuncia Número de tokens realmente colocados en `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="a9c73-111">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9c73-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9c73-112">Return Value</span></span>  
  
|<span data-ttu-id="a9c73-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9c73-113">HRESULT</span></span>|<span data-ttu-id="a9c73-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9c73-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a9c73-115">`EnumAssemblyRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9c73-115">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a9c73-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="a9c73-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="a9c73-117">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="a9c73-117">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9c73-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9c73-118">Requirements</span></span>  

 <span data-ttu-id="a9c73-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9c73-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9c73-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a9c73-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9c73-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9c73-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9c73-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9c73-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c73-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9c73-123">See also</span></span>

- [<span data-ttu-id="a9c73-124">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9c73-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
