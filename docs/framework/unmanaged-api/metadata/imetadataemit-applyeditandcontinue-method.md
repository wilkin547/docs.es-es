---
title: "IMetaDataEmit::ApplyEditAndContinue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.ApplyEditAndContinue
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4d6f378c4da884cffc6827f700586cee745642b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="666c3-102">IMetaDataEmit::ApplyEditAndContinue (Método)</span><span class="sxs-lookup"><span data-stu-id="666c3-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="666c3-103">Actualiza el ámbito de ensamblado actual con los cambios realizados en los metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="666c3-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="666c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="666c3-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="666c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="666c3-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="666c3-106">[in] Puntero a un <<!--zzxref:IUnknown --> `IUnknown`> objeto que representa los metadatos delta del archivo ejecutable portable (PE).</span><span class="sxs-lookup"><span data-stu-id="666c3-106">[in] Pointer to an <<!--zzxref:IUnknown --> `IUnknown`> object that represents the delta metadata from the portable executable (PE) file.</span></span>  
  
 <span data-ttu-id="666c3-107">Los metadatos delta están el bloque de metadatos que incluyen los cambios realizados en la copia de los metadatos del módulo real.</span><span class="sxs-lookup"><span data-stu-id="666c3-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="666c3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="666c3-108">Requirements</span></span>  
 <span data-ttu-id="666c3-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="666c3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="666c3-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="666c3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="666c3-111">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="666c3-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="666c3-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="666c3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666c3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="666c3-113">See Also</span></span>  
 [<span data-ttu-id="666c3-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="666c3-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="666c3-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="666c3-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
