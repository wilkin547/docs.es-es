---
title: "ICorPublishProcess::GetProcessID (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.GetProcessID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a048255e075b01f4c3c7635038b22ab581032524
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="68d7e-102">ICorPublishProcess::GetProcessID (Método)</span><span class="sxs-lookup"><span data-stu-id="68d7e-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="68d7e-103">Obtiene el identificador de sistema operativo para este proceso.</span><span class="sxs-lookup"><span data-stu-id="68d7e-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68d7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68d7e-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68d7e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="68d7e-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="68d7e-106">[out] Un puntero al valor del identificador del proceso representado por este [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="68d7e-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68d7e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68d7e-107">Requirements</span></span>  
 <span data-ttu-id="68d7e-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68d7e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68d7e-109">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="68d7e-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="68d7e-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68d7e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68d7e-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68d7e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d7e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="68d7e-112">See Also</span></span>  
 [<span data-ttu-id="68d7e-113">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68d7e-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
