---
description: 'Más información acerca de: ICLRTaskManager:: GetCurrentTaskType ((método)'
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
ms.openlocfilehash: 984cc490123d6146737d3f018fdf712c7c528635
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799491"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="35ecb-103">ICLRTaskManager::GetCurrentTaskType (Método)</span><span class="sxs-lookup"><span data-stu-id="35ecb-103">ICLRTaskManager::GetCurrentTaskType Method</span></span>

<span data-ttu-id="35ecb-104">Obtiene el tipo de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="35ecb-104">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35ecb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35ecb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35ecb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35ecb-106">Parameters</span></span>  

 `pTaskType`  
 <span data-ttu-id="35ecb-107">enuncia Un puntero a un valor de la enumeración [ETaskType (](etasktype-enumeration.md) que indica el tipo de tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="35ecb-107">[out] A pointer to a value of the [ETaskType](etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35ecb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35ecb-108">Requirements</span></span>  

 <span data-ttu-id="35ecb-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35ecb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35ecb-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="35ecb-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35ecb-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35ecb-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35ecb-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35ecb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35ecb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="35ecb-113">See also</span></span>

- [<span data-ttu-id="35ecb-114">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35ecb-114">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
