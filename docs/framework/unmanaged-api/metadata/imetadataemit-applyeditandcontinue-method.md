---
description: 'Más información sobre: IMetaDataEmit:: Applyeditandcontinue ((método)'
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
ms.openlocfilehash: 46454c4141aa220b43820307c86765a1827251df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753502"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="5675b-103">IMetaDataEmit::ApplyEditAndContinue (Método)</span><span class="sxs-lookup"><span data-stu-id="5675b-103">IMetaDataEmit::ApplyEditAndContinue Method</span></span>

<span data-ttu-id="5675b-104">Actualiza el ámbito de ensamblado actual con los cambios realizados en los metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="5675b-104">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5675b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5675b-105">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5675b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5675b-106">Parameters</span></span>  

 `pImport`  
 <span data-ttu-id="5675b-107">\[en \] puntero a un objeto [IUnknown](/cpp/atl/iunknown) que representa los metadatos Delta del archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="5675b-107">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="5675b-108">Los metadatos Delta son el bloque de metadatos que incluye los cambios que se realizaron en la copia de los metadatos reales del módulo.</span><span class="sxs-lookup"><span data-stu-id="5675b-108">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5675b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5675b-109">Requirements</span></span>  

 <span data-ttu-id="5675b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5675b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5675b-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5675b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5675b-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5675b-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5675b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5675b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5675b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5675b-114">See also</span></span>

- [<span data-ttu-id="5675b-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5675b-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5675b-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5675b-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
