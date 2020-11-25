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
ms.openlocfilehash: 718e6f3f19a5c368091c8a8aad3bd1f6598228df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727286"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="890f5-102">IHostTaskManager::GetStackGuarantee (Método)</span><span class="sxs-lookup"><span data-stu-id="890f5-102">IHostTaskManager::GetStackGuarantee Method</span></span>

<span data-ttu-id="890f5-103">Obtiene la cantidad de espacio de pila que se garantiza que está disponible después de que se complete una operación de pila, pero antes del cierre de un proceso.</span><span class="sxs-lookup"><span data-stu-id="890f5-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="890f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="890f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="890f5-105">Parameters</span></span>  

 `pGuarantee`  
 <span data-ttu-id="890f5-106">enuncia Puntero al número de bytes que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="890f5-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="890f5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="890f5-107">Requirements</span></span>  

 <span data-ttu-id="890f5-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="890f5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="890f5-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="890f5-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="890f5-110">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="890f5-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="890f5-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="890f5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890f5-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="890f5-112">See also</span></span>

- [<span data-ttu-id="890f5-113">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="890f5-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
