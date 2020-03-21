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
ms.openlocfilehash: f876187624d066b9e672fbf44a984d6d02a54c43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175881"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="dc78b-102">IMetaDataEmit::ApplyEditAndContinue (Método)</span><span class="sxs-lookup"><span data-stu-id="dc78b-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="dc78b-103">Actualiza el ámbito del ensamblado actual con los cambios realizados en los metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="dc78b-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc78b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc78b-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc78b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc78b-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="dc78b-106">\[en\] Puntero a un [objeto IUnknown](/cpp/atl/iunknown) que representa los metadatos delta del archivo ejecutable portátil (PE).</span><span class="sxs-lookup"><span data-stu-id="dc78b-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="dc78b-107">Los metadatos delta son el bloque de metadatos que incluye los cambios realizados en la copia de los metadatos reales del módulo.</span><span class="sxs-lookup"><span data-stu-id="dc78b-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc78b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc78b-108">Requirements</span></span>  
 <span data-ttu-id="dc78b-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc78b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc78b-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dc78b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc78b-111">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc78b-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc78b-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc78b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc78b-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc78b-113">See also</span></span>

- [<span data-ttu-id="dc78b-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc78b-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="dc78b-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc78b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
