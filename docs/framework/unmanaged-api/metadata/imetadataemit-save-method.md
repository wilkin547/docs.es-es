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
ms.openlocfilehash: cef238239417a0a30cd94eaa8bd60968cfa78859
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722003"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="87435-102">IMetaDataEmit::Save (Método)</span><span class="sxs-lookup"><span data-stu-id="87435-102">IMetaDataEmit::Save Method</span></span>

<span data-ttu-id="87435-103">Guarda todos los metadatos en el ámbito actual en el archivo en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="87435-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87435-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87435-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87435-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87435-105">Parameters</span></span>  

 `wzFile`  
 <span data-ttu-id="87435-106">de Nombre del archivo en el que se va a guardar.</span><span class="sxs-lookup"><span data-stu-id="87435-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="87435-107">Si este valor es null, la copia en memoria se guardará en la última ubicación utilizada.</span><span class="sxs-lookup"><span data-stu-id="87435-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="87435-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="87435-108">[in] Reserved.</span></span> <span data-ttu-id="87435-109">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="87435-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87435-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87435-110">Requirements</span></span>  

 <span data-ttu-id="87435-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87435-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87435-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="87435-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87435-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87435-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87435-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87435-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87435-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87435-115">See also</span></span>

- [<span data-ttu-id="87435-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87435-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="87435-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87435-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
