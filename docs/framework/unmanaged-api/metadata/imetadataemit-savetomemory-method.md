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
ms.openlocfilehash: ccf82531eb1f78bcfc6762d10d53ffee59f30ad8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003968"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="7b6b5-102">IMetaDataEmit::SaveToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="7b6b5-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="7b6b5-103">Guarda todos los metadatos del ámbito actual en el área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="7b6b5-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b6b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b6b5-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b6b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b6b5-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="7b6b5-106">enuncia Dirección en la que se comienzan a escribir los metadatos.</span><span class="sxs-lookup"><span data-stu-id="7b6b5-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="7b6b5-107">de Tamaño, en bytes, de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="7b6b5-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b6b5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b6b5-108">Requirements</span></span>  
 <span data-ttu-id="7b6b5-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b6b5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b6b5-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7b6b5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b6b5-111">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7b6b5-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b6b5-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b6b5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b6b5-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b6b5-113">See also</span></span>

- [<span data-ttu-id="7b6b5-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b6b5-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7b6b5-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b6b5-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
