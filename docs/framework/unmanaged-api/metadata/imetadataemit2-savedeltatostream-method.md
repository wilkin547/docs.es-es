---
title: "IMetaDataEmit2::SaveDeltaToStream (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bcfd90da200e04e5834b21ea84a3a84acc5b732d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="9f227-102">IMetaDataEmit2::SaveDeltaToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="9f227-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="9f227-103">Guarda los cambios de la sesión actual de editar y continuar en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="9f227-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f227-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f227-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f227-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f227-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="9f227-106">[in] Un puntero de interfaz a la secuencia de escritura que se va a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="9f227-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="9f227-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="9f227-107">[in] Reserved.</span></span> <span data-ttu-id="9f227-108">Este valor debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="9f227-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f227-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f227-109">Requirements</span></span>  
 <span data-ttu-id="9f227-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f227-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f227-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9f227-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f227-112">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f227-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f227-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f227-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f227-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f227-114">See Also</span></span>  
 [<span data-ttu-id="9f227-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f227-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="9f227-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f227-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
