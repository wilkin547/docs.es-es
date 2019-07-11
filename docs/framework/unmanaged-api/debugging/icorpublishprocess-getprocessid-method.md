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
ms.openlocfilehash: 29427bab938437c40d0edb5676a2f8f76cbb6691
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764861"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="db90f-102">ICorPublishProcess::GetProcessID (Método)</span><span class="sxs-lookup"><span data-stu-id="db90f-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="db90f-103">Obtiene el identificador de sistema operativo de este proceso.</span><span class="sxs-lookup"><span data-stu-id="db90f-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db90f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db90f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db90f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db90f-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="db90f-106">[out] Un puntero al identificador del proceso representado por este [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="db90f-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db90f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db90f-107">Requirements</span></span>  
 <span data-ttu-id="db90f-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db90f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db90f-109">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="db90f-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="db90f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db90f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db90f-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db90f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db90f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="db90f-112">See also</span></span>

- [<span data-ttu-id="db90f-113">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db90f-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
