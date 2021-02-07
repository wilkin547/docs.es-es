---
description: 'Más información sobre: IMetaDataEmit:: Savetomemory ((método)'
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
ms.openlocfilehash: b5fbca2c3ce06398de72bf2690108077545fef9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745806"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="5d7bd-103">IMetaDataEmit::SaveToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="5d7bd-103">IMetaDataEmit::SaveToMemory Method</span></span>

<span data-ttu-id="5d7bd-104">Guarda todos los metadatos del ámbito actual en el área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="5d7bd-104">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d7bd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d7bd-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d7bd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d7bd-106">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="5d7bd-107">enuncia Dirección en la que se comienzan a escribir los metadatos.</span><span class="sxs-lookup"><span data-stu-id="5d7bd-107">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="5d7bd-108">de Tamaño, en bytes, de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="5d7bd-108">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d7bd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d7bd-109">Requirements</span></span>  

 <span data-ttu-id="5d7bd-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d7bd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d7bd-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5d7bd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d7bd-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d7bd-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d7bd-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d7bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d7bd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d7bd-114">See also</span></span>

- [<span data-ttu-id="5d7bd-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d7bd-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5d7bd-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d7bd-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
