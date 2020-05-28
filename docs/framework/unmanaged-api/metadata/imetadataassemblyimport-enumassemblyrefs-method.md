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
ms.openlocfilehash: 1b9700455da82fc7f4a39d4c208ac0b18ef79722
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009124"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="1c5ce-102">IMetaDataAssemblyImport::EnumAssemblyRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="1c5ce-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="1c5ce-103">Enumera las `mdAssemblyRef` instancias de definidas en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c5ce-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c5ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c5ce-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c5ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c5ce-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1c5ce-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="1c5ce-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1c5ce-107">Debe ser un valor NULL cuando `EnumAssemblyRefs` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="1c5ce-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="1c5ce-108">enuncia Enumeración de los `mdAssemblyRef` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="1c5ce-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1c5ce-109">de Número máximo de tokens que se pueden colocar en la `rAssemblyRefs` matriz.</span><span class="sxs-lookup"><span data-stu-id="1c5ce-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1c5ce-110">enuncia Número de tokens realmente colocados en `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="1c5ce-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c5ce-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1c5ce-111">Return Value</span></span>  
  
|<span data-ttu-id="1c5ce-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c5ce-112">HRESULT</span></span>|<span data-ttu-id="1c5ce-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c5ce-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1c5ce-114">`EnumAssemblyRefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1c5ce-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1c5ce-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="1c5ce-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="1c5ce-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="1c5ce-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c5ce-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c5ce-117">Requirements</span></span>  
 <span data-ttu-id="1c5ce-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c5ce-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c5ce-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1c5ce-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c5ce-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1c5ce-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c5ce-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c5ce-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5ce-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c5ce-122">See also</span></span>

- [<span data-ttu-id="1c5ce-123">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c5ce-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
