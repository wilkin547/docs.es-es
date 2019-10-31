---
title: ICLRTaskManager::GetCurrentTaskType (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
ms.openlocfilehash: 848255d44ce8637182f18288d30151a3f0df0912
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092164"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="55117-102">ICLRTaskManager::GetCurrentTaskType (Método)</span><span class="sxs-lookup"><span data-stu-id="55117-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="55117-103">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="55117-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55117-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55117-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55117-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55117-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="55117-106">enuncia Un puntero a un valor de la enumeración [ETaskType (](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) que indica el tipo de tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="55117-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55117-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55117-107">Requirements</span></span>  
 <span data-ttu-id="55117-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55117-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55117-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="55117-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55117-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55117-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55117-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55117-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55117-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="55117-112">See also</span></span>

- [<span data-ttu-id="55117-113">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55117-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
