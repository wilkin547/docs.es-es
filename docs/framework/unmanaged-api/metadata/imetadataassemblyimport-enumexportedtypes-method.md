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
ms.openlocfilehash: 514488c6e0d2e89de0d8ee483def485ec9f3ef25
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009111"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="3989c-102">IMetaDataAssemblyImport::EnumExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="3989c-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="3989c-103">Enumera los tipos exportados a los que se hace referencia en el manifiesto del ensamblado en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="3989c-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3989c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3989c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3989c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3989c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3989c-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="3989c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3989c-107">Debe ser un valor NULL cuando `EnumExportedTypes` se llama al método por primera vez.</span><span class="sxs-lookup"><span data-stu-id="3989c-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="3989c-108">enuncia Enumeración de los `mdExportedType` tokens de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3989c-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3989c-109">de Número máximo de `mdExportedType` tokens que se pueden colocar en la `rExportedTypes` matriz.</span><span class="sxs-lookup"><span data-stu-id="3989c-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3989c-110">enuncia Número de `mdExportedType` tokens realmente colocados en `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="3989c-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3989c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3989c-111">Return Value</span></span>  
  
|<span data-ttu-id="3989c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3989c-112">HRESULT</span></span>|<span data-ttu-id="3989c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3989c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3989c-114">`EnumExportedTypes`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3989c-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3989c-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="3989c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3989c-116">En este caso, `pcTokens` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="3989c-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3989c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3989c-117">Requirements</span></span>  
 <span data-ttu-id="3989c-118">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3989c-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3989c-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3989c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3989c-120">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3989c-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3989c-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3989c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3989c-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3989c-122">See also</span></span>

- [<span data-ttu-id="3989c-123">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3989c-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
