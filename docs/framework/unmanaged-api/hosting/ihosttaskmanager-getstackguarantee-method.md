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
ms.openlocfilehash: 22ec34c82d0f8e550dfc8941f2c048ebed6cf1d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133036"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="708fc-102">IHostTaskManager::GetStackGuarantee (Método)</span><span class="sxs-lookup"><span data-stu-id="708fc-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="708fc-103">Obtiene la cantidad de espacio de pila que se garantiza que está disponible después de que se complete una operación de pila, pero antes del cierre de un proceso.</span><span class="sxs-lookup"><span data-stu-id="708fc-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="708fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="708fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="708fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="708fc-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="708fc-106">enuncia Puntero al número de bytes que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="708fc-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="708fc-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="708fc-107">Requirements</span></span>  
 <span data-ttu-id="708fc-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="708fc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="708fc-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="708fc-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="708fc-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="708fc-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="708fc-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="708fc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708fc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="708fc-112">See also</span></span>

- [<span data-ttu-id="708fc-113">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708fc-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
