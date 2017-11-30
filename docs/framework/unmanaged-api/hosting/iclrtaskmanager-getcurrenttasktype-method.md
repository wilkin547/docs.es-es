---
title: "ICLRTaskManager::GetCurrentTaskType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.GetCurrentTaskType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f4c1114f4d90c10d8ca40b1b6fc6e071eff5b3f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="ce349-102">ICLRTaskManager::GetCurrentTaskType (Método)</span><span class="sxs-lookup"><span data-stu-id="ce349-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="ce349-103">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="ce349-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce349-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce349-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce349-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce349-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="ce349-106">[out] Un puntero a un valor de la [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeración que indica el tipo de tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="ce349-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce349-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce349-107">Requirements</span></span>  
 <span data-ttu-id="ce349-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce349-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce349-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce349-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce349-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce349-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce349-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce349-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce349-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce349-112">See Also</span></span>  
 [<span data-ttu-id="ce349-113">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce349-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
