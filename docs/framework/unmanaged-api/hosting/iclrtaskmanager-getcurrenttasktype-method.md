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
ms.openlocfilehash: 684b94471c53701c5ebe1dc7e7593eae16ad50fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728789"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="95efd-102">ICLRTaskManager::GetCurrentTaskType (Método)</span><span class="sxs-lookup"><span data-stu-id="95efd-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>

<span data-ttu-id="95efd-103">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="95efd-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95efd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95efd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95efd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95efd-105">Parameters</span></span>  

 `pTaskType`  
 <span data-ttu-id="95efd-106">enuncia Un puntero a un valor de la enumeración [ETaskType (](etasktype-enumeration.md) que indica el tipo de tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="95efd-106">[out] A pointer to a value of the [ETaskType](etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95efd-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95efd-107">Requirements</span></span>  

 <span data-ttu-id="95efd-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95efd-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95efd-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="95efd-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95efd-110">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95efd-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95efd-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95efd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95efd-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95efd-112">See also</span></span>

- [<span data-ttu-id="95efd-113">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95efd-113">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
