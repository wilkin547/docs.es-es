---
title: "IMetaDataEmit2::SaveDeltaToMemory (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SaveDeltaToMemory
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8c3148cdb417d627afd9ba007fb9892b47dcef3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="d26c3-102">IMetaDataEmit2::SaveDeltaToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="d26c3-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="d26c3-103">Guarda los cambios de la sesión actual de editar y continuar en la memoria.</span><span class="sxs-lookup"><span data-stu-id="d26c3-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d26c3-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d26c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d26c3-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="d26c3-106">[out] La dirección en la que se va a empezar a escribir las diferencias de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d26c3-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="d26c3-107">[in] El tamaño de los cambios.</span><span class="sxs-lookup"><span data-stu-id="d26c3-107">[in] The size of the changes.</span></span> <span data-ttu-id="d26c3-108">Use [IMetaDataEmit2:: GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) para determinar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="d26c3-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d26c3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d26c3-109">Requirements</span></span>  
 <span data-ttu-id="d26c3-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d26c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d26c3-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d26c3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d26c3-112">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d26c3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d26c3-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d26c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26c3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d26c3-114">See Also</span></span>  
 [<span data-ttu-id="d26c3-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d26c3-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="d26c3-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d26c3-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
