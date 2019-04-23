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
ms.openlocfilehash: ea1c1f998febccbc80fb10cef5a8dfd229e1987e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095951"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="39aea-102">IHostTaskManager::GetStackGuarantee (Método)</span><span class="sxs-lookup"><span data-stu-id="39aea-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="39aea-103">Obtiene la cantidad de espacio de pila que se garantiza que estarán disponibles después de que finalice una operación de la pila, pero antes del cierre de un proceso.</span><span class="sxs-lookup"><span data-stu-id="39aea-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39aea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39aea-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39aea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39aea-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="39aea-106">[out] Un puntero al número de bytes que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="39aea-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39aea-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39aea-107">Requirements</span></span>  
 <span data-ttu-id="39aea-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39aea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39aea-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39aea-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39aea-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39aea-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39aea-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39aea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39aea-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="39aea-112">See also</span></span>

- [<span data-ttu-id="39aea-113">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39aea-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
