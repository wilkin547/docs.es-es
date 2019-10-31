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
ms.openlocfilehash: 728e8bdbce7f93176324d8f80261030f8cbae283
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140410"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="ccfee-102">ICorPublishProcess::GetProcessID (Método)</span><span class="sxs-lookup"><span data-stu-id="ccfee-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="ccfee-103">Obtiene el identificador del sistema operativo para este proceso.</span><span class="sxs-lookup"><span data-stu-id="ccfee-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccfee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccfee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccfee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccfee-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="ccfee-106">enuncia Puntero al identificador del proceso representado por este objeto [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ccfee-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccfee-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccfee-107">Requirements</span></span>  
 <span data-ttu-id="ccfee-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccfee-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccfee-109">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="ccfee-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ccfee-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccfee-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccfee-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccfee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfee-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccfee-112">See also</span></span>

- [<span data-ttu-id="ccfee-113">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccfee-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
