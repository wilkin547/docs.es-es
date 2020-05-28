---
title: IMetaDataEmit::Save (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: 23f6a301c4c11be92e05dbac0d4f69817d857a28
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003971"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="39590-102">IMetaDataEmit::Save (Método)</span><span class="sxs-lookup"><span data-stu-id="39590-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="39590-103">Guarda todos los metadatos en el ámbito actual en el archivo en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="39590-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39590-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39590-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39590-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39590-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="39590-106">de Nombre del archivo en el que se va a guardar.</span><span class="sxs-lookup"><span data-stu-id="39590-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="39590-107">Si este valor es null, la copia en memoria se guardará en la última ubicación utilizada.</span><span class="sxs-lookup"><span data-stu-id="39590-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="39590-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="39590-108">[in] Reserved.</span></span> <span data-ttu-id="39590-109">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="39590-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39590-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39590-110">Requirements</span></span>  
 <span data-ttu-id="39590-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39590-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39590-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="39590-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39590-113">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="39590-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39590-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39590-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39590-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39590-115">See also</span></span>

- [<span data-ttu-id="39590-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39590-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="39590-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39590-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
