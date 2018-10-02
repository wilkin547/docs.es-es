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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: faa9bc412e67e0e49ee969bd8b246a424fe628a0
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48034342"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="2f548-102">IMetaDataEmit::ApplyEditAndContinue (Método)</span><span class="sxs-lookup"><span data-stu-id="2f548-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="2f548-103">El ámbito de ensamblado actual se actualiza con los cambios realizados en los metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="2f548-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f548-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f548-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f548-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f548-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="2f548-106">\[en\] puntero a un [IUnknown](/cpp/atl/iunknown) objeto que representa los metadatos delta del archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="2f548-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="2f548-107">Los metadatos delta están el bloque de metadatos que incluyen los cambios realizados en la copia de los metadatos del módulo real.</span><span class="sxs-lookup"><span data-stu-id="2f548-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f548-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f548-108">Requirements</span></span>  
 <span data-ttu-id="2f548-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f548-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f548-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f548-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f548-111">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f548-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f548-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f548-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f548-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f548-113">See Also</span></span>  
 [<span data-ttu-id="2f548-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2f548-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="2f548-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2f548-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
