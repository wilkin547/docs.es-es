---
title: IHostTaskManager::GetStackGuarantee (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 100bb73356379d2f251513bbbed0cf1e90752ff5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494381"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="fb7b7-102">IHostTaskManager::GetStackGuarantee (Método)</span><span class="sxs-lookup"><span data-stu-id="fb7b7-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="fb7b7-103">Obtiene la cantidad de espacio de pila que se garantiza que estarán disponibles después de que finalice una operación de la pila, pero antes del cierre de un proceso.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb7b7-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb7b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb7b7-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="fb7b7-106">[out] Un puntero al número de bytes que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="fb7b7-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb7b7-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb7b7-107">Requirements</span></span>  
 <span data-ttu-id="fb7b7-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb7b7-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb7b7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb7b7-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb7b7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb7b7-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7b7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7b7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb7b7-112">See also</span></span>
- [<span data-ttu-id="fb7b7-113">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb7b7-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
