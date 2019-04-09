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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2963e2a31fd62470e3ed6933edb38119d286071b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59071979"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="66ea0-102">ICLRTaskManager::GetCurrentTaskType (Método)</span><span class="sxs-lookup"><span data-stu-id="66ea0-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="66ea0-103">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="66ea0-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66ea0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66ea0-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66ea0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66ea0-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="66ea0-106">[out] Un puntero a un valor de la [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeración que indica el tipo de tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="66ea0-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66ea0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66ea0-107">Requirements</span></span>  
 <span data-ttu-id="66ea0-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66ea0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66ea0-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="66ea0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66ea0-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66ea0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="66ea0-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="66ea0-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66ea0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="66ea0-112">See also</span></span>

- [<span data-ttu-id="66ea0-113">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66ea0-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
