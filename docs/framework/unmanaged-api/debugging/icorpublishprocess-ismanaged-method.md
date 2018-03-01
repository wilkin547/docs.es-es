---
title: "ICorPublishProcess::IsManaged (Método)"
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
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21fdb09820acb6357fe1457d2f96c3319b3152a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="5a384-102">ICorPublishProcess::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="5a384-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="5a384-103">Obtiene un valor que indica si el proceso al que hace referencia este [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) se sabe que tienen código administrado.</span><span class="sxs-lookup"><span data-stu-id="5a384-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a384-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a384-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a384-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a384-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="5a384-106">[out] Un puntero a un valor booleano que indica si el proceso tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="5a384-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="5a384-107">El valor es `true` si el proceso tiene código administrado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="5a384-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a384-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a384-108">Remarks</span></span>  
 <span data-ttu-id="5a384-109">Desde la versión actual de `ICorPublishProcess` permite el acceso sólo a los procesos que tienen código, administrado `IsManaged` siempre devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="5a384-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a384-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a384-110">Requirements</span></span>  
 <span data-ttu-id="5a384-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a384-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a384-112">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="5a384-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5a384-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a384-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a384-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a384-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a384-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a384-115">See Also</span></span>  
 [<span data-ttu-id="5a384-116">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a384-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
