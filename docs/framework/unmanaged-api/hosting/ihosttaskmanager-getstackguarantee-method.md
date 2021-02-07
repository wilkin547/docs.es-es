---
description: 'Más información acerca de: IHostTaskManager:: Getstackguarantee ((método)'
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
ms.openlocfilehash: 6c8bd9839ea0c1fdb72fbbd296061d1a2b6edfe1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753801"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="53256-103">IHostTaskManager::GetStackGuarantee (Método)</span><span class="sxs-lookup"><span data-stu-id="53256-103">IHostTaskManager::GetStackGuarantee Method</span></span>

<span data-ttu-id="53256-104">Obtiene la cantidad de espacio de pila que se garantiza que está disponible después de que se complete una operación de pila, pero antes del cierre de un proceso.</span><span class="sxs-lookup"><span data-stu-id="53256-104">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53256-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53256-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53256-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53256-106">Parameters</span></span>  

 `pGuarantee`  
 <span data-ttu-id="53256-107">enuncia Puntero al número de bytes que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="53256-107">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53256-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53256-108">Requirements</span></span>  

 <span data-ttu-id="53256-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53256-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53256-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53256-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53256-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53256-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53256-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53256-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53256-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="53256-113">See also</span></span>

- [<span data-ttu-id="53256-114">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53256-114">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
