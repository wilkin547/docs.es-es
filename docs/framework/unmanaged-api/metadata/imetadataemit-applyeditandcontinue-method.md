---
title: IMetaDataEmit::ApplyEditAndContinue (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
ms.openlocfilehash: 0cc84893c4937bf6b23eae0d63b92b3b871901dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700579"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="7ae77-102">IMetaDataEmit::ApplyEditAndContinue (Método)</span><span class="sxs-lookup"><span data-stu-id="7ae77-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>

<span data-ttu-id="7ae77-103">Actualiza el ámbito de ensamblado actual con los cambios realizados en los metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="7ae77-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ae77-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ae77-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ae77-105">Parameters</span></span>  

 `pImport`  
 <span data-ttu-id="7ae77-106">\[en \] puntero a un objeto [IUnknown](/cpp/atl/iunknown) que representa los metadatos Delta del archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="7ae77-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="7ae77-107">Los metadatos Delta son el bloque de metadatos que incluye los cambios que se realizaron en la copia de los metadatos reales del módulo.</span><span class="sxs-lookup"><span data-stu-id="7ae77-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae77-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ae77-108">Requirements</span></span>  

 <span data-ttu-id="7ae77-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ae77-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae77-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7ae77-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ae77-111">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ae77-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ae77-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae77-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae77-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ae77-113">See also</span></span>

- [<span data-ttu-id="7ae77-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ae77-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7ae77-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ae77-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
