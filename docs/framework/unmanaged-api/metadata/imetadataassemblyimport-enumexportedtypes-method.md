---
description: 'Más información sobre: IMetaDataAssemblyImport:: Enumexportedtypes ((método)'
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
ms.openlocfilehash: ecddcbd87586f5f61c57f8c04ea3bd68dc652839
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678034"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="a3b4a-103">IMetaDataAssemblyImport::EnumExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="a3b4a-103">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>

<span data-ttu-id="a3b4a-104">Enumera los tipos exportados a los que se hace referencia en el manifiesto del ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="a3b4a-104">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3b4a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3b4a-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3b4a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3b4a-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a3b4a-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="a3b4a-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a3b4a-108">Debe ser un valor NULL cuando `EnumExportedTypes` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="a3b4a-108">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="a3b4a-109">enuncia Enumeración de los `mdExportedType` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="a3b4a-109">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a3b4a-110">de Número máximo de `mdExportedType` tokens que se pueden colocar en la `rExportedTypes` matriz.</span><span class="sxs-lookup"><span data-stu-id="a3b4a-110">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a3b4a-111">enuncia Número de `mdExportedType` tokens realmente colocados en `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="a3b4a-111">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3b4a-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3b4a-112">Return Value</span></span>  
  
|<span data-ttu-id="a3b4a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3b4a-113">HRESULT</span></span>|<span data-ttu-id="a3b4a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3b4a-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a3b4a-115">`EnumExportedTypes` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3b4a-115">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a3b4a-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="a3b4a-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="a3b4a-117">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="a3b4a-117">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3b4a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3b4a-118">Requirements</span></span>  

 <span data-ttu-id="a3b4a-119">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3b4a-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3b4a-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a3b4a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3b4a-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3b4a-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3b4a-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3b4a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b4a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3b4a-123">See also</span></span>

- [<span data-ttu-id="a3b4a-124">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3b4a-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
