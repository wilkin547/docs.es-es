---
title: IMetaDataEmit::SaveToMemory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: 1cd5e34d6afefab2fda7e20d4bf73b373ad42787
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688606"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="5dc68-102">IMetaDataEmit::SaveToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="5dc68-102">IMetaDataEmit::SaveToMemory Method</span></span>

<span data-ttu-id="5dc68-103">Guarda todos los metadatos del ámbito actual en el área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="5dc68-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dc68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5dc68-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dc68-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5dc68-105">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="5dc68-106">enuncia Dirección en la que se comienzan a escribir los metadatos.</span><span class="sxs-lookup"><span data-stu-id="5dc68-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="5dc68-107">de Tamaño, en bytes, de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="5dc68-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dc68-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dc68-108">Requirements</span></span>  

 <span data-ttu-id="5dc68-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc68-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc68-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5dc68-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5dc68-111">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5dc68-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dc68-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dc68-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc68-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5dc68-113">See also</span></span>

- [<span data-ttu-id="5dc68-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dc68-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5dc68-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dc68-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
