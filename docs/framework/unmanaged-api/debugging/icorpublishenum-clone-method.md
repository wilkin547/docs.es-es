---
title: ICorPublishEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12d9e468027e88cc74900364459f83d7e5125a9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423811"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="a040f-102">ICorPublishEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="a040f-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="a040f-103">Crea una copia de esta [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="a040f-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a040f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a040f-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a040f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a040f-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="a040f-106">[out] Un puntero a la dirección de un `ICorPublishEnum` objeto que es una copia de este `ICorPublishEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="a040f-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a040f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a040f-107">Requirements</span></span>  
 <span data-ttu-id="a040f-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a040f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a040f-109">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="a040f-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a040f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a040f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a040f-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a040f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a040f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a040f-112">See Also</span></span>  
 [<span data-ttu-id="a040f-113">ICorPublishEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a040f-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
