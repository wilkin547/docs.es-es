---
title: IMetaDataAssemblyImport::EnumExportedTypes (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708899"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="2376e-102">IMetaDataAssemblyImport::EnumExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="2376e-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>

<span data-ttu-id="2376e-103">Enumera los tipos exportados a los que se hace referencia en el manifiesto del ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="2376e-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2376e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2376e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2376e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2376e-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="2376e-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="2376e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2376e-107">Debe ser un valor NULL cuando `EnumExportedTypes` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="2376e-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="2376e-108">enuncia Enumeración de los `mdExportedType` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2376e-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2376e-109">de Número máximo de `mdExportedType` tokens que se pueden colocar en la `rExportedTypes` matriz.</span><span class="sxs-lookup"><span data-stu-id="2376e-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2376e-110">enuncia Número de `mdExportedType` tokens realmente colocados en `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="2376e-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2376e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2376e-111">Return Value</span></span>  
  
|<span data-ttu-id="2376e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2376e-112">HRESULT</span></span>|<span data-ttu-id="2376e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2376e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2376e-114">`EnumExportedTypes` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2376e-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2376e-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="2376e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2376e-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="2376e-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2376e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2376e-117">Requirements</span></span>  

 <span data-ttu-id="2376e-118">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2376e-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2376e-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2376e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2376e-120">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2376e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2376e-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2376e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2376e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2376e-122">See also</span></span>

- [<span data-ttu-id="2376e-123">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2376e-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
