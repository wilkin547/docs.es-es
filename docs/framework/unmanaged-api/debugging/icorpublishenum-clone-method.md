---
title: "ICorPublishEnum::Clone (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishEnum.Clone
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e230c7ed21b802f4e1784b8e8ec5ba6646bd8666
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="7e691-102">ICorPublishEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="7e691-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="7e691-103">Crea una copia de esta [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="7e691-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e691-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e691-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e691-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e691-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="7e691-106">[out] Un puntero a la dirección de un `ICorPublishEnum` objeto que es una copia de este `ICorPublishEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="7e691-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e691-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e691-107">Requirements</span></span>  
 <span data-ttu-id="7e691-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e691-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e691-109">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="7e691-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7e691-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e691-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e691-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e691-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e691-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e691-112">See Also</span></span>  
 [<span data-ttu-id="7e691-113">ICorPublishEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e691-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
