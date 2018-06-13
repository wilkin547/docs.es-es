---
title: ICorPublishProcess::GetProcessID (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91e1697366bd3ee95fd040ee261d68417a8125e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423613"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="3651f-102">ICorPublishProcess::GetProcessID (Método)</span><span class="sxs-lookup"><span data-stu-id="3651f-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="3651f-103">Obtiene el identificador de sistema operativo para este proceso.</span><span class="sxs-lookup"><span data-stu-id="3651f-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3651f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3651f-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3651f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3651f-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="3651f-106">[out] Un puntero al valor del identificador del proceso representado por este [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="3651f-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3651f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3651f-107">Requirements</span></span>  
 <span data-ttu-id="3651f-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3651f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3651f-109">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3651f-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3651f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3651f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3651f-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3651f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3651f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3651f-112">See Also</span></span>  
 [<span data-ttu-id="3651f-113">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3651f-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
