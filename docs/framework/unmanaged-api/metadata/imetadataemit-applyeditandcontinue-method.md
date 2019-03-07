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
ms.openlocfilehash: d0558154dc64ca95a691f36fb67586d570caa888
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484997"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="0583f-102">IMetaDataEmit::ApplyEditAndContinue (Método)</span><span class="sxs-lookup"><span data-stu-id="0583f-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="0583f-103">El ámbito de ensamblado actual se actualiza con los cambios realizados en los metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="0583f-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0583f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0583f-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0583f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0583f-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="0583f-106">\[en\] puntero a un [IUnknown](/cpp/atl/iunknown) objeto que representa los metadatos delta del archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="0583f-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="0583f-107">Los metadatos delta están el bloque de metadatos que incluyen los cambios realizados en la copia de los metadatos del módulo real.</span><span class="sxs-lookup"><span data-stu-id="0583f-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0583f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0583f-108">Requirements</span></span>  
 <span data-ttu-id="0583f-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0583f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0583f-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="0583f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0583f-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0583f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0583f-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0583f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0583f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0583f-113">See also</span></span>
- [<span data-ttu-id="0583f-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0583f-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0583f-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0583f-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
