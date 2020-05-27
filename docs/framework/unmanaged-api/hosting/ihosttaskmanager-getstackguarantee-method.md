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
ms.openlocfilehash: d76242eb8539f2e8dffbf39b7eaf595664bdce8e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842028"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="2233f-102">IHostTaskManager::GetStackGuarantee (Método)</span><span class="sxs-lookup"><span data-stu-id="2233f-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="2233f-103">Obtiene la cantidad de espacio de pila que se garantiza que está disponible después de que se complete una operación de pila, pero antes del cierre de un proceso.</span><span class="sxs-lookup"><span data-stu-id="2233f-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2233f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2233f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2233f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2233f-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="2233f-106">enuncia Puntero al número de bytes que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="2233f-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2233f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2233f-107">Requirements</span></span>  
 <span data-ttu-id="2233f-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2233f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2233f-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2233f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2233f-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2233f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2233f-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2233f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2233f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2233f-112">See also</span></span>

- [<span data-ttu-id="2233f-113">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2233f-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
