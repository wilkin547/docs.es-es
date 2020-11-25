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
ms.openlocfilehash: 18cd9dd14e615a7e76bfff30c9ae584305bd1907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708948"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="44dc7-102">IMetaDataAssemblyImport::EnumAssemblyRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="44dc7-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>

<span data-ttu-id="44dc7-103">Enumera las `mdAssemblyRef` instancias de definidas en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="44dc7-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44dc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44dc7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44dc7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44dc7-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="44dc7-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="44dc7-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="44dc7-107">Debe ser un valor NULL cuando `EnumAssemblyRefs` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="44dc7-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="44dc7-108">enuncia Enumeración de los `mdAssemblyRef` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="44dc7-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="44dc7-109">de Número máximo de tokens que se pueden colocar en la `rAssemblyRefs` matriz.</span><span class="sxs-lookup"><span data-stu-id="44dc7-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="44dc7-110">enuncia Número de tokens realmente colocados en `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="44dc7-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44dc7-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="44dc7-111">Return Value</span></span>  
  
|<span data-ttu-id="44dc7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="44dc7-112">HRESULT</span></span>|<span data-ttu-id="44dc7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="44dc7-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="44dc7-114">`EnumAssemblyRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="44dc7-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="44dc7-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="44dc7-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="44dc7-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="44dc7-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44dc7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44dc7-117">Requirements</span></span>  

 <span data-ttu-id="44dc7-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44dc7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44dc7-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="44dc7-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44dc7-120">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44dc7-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44dc7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44dc7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44dc7-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44dc7-122">See also</span></span>

- [<span data-ttu-id="44dc7-123">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44dc7-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
