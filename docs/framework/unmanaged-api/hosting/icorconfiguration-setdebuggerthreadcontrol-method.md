---
title: ICorConfiguration::SetDebuggerThreadControl (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
ms.openlocfilehash: 05df50d80c6b8962b3bdfe2708d5f9d30c58aaea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723927"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="537d2-102">ICorConfiguration::SetDebuggerThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="537d2-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>

<span data-ttu-id="537d2-103">Establece la interfaz de devolución de llamada a la que los servicios de depuración llamarán como subprocesos Common Language Runtime (CLR) se bloquean y desbloquean para la depuración.</span><span class="sxs-lookup"><span data-stu-id="537d2-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="537d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="537d2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="537d2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="537d2-105">Parameters</span></span>  

 `pDebuggerThreadControl`  
 <span data-ttu-id="537d2-106">de Un puntero a un objeto [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) que notifica al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="537d2-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="537d2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="537d2-107">Requirements</span></span>  

 <span data-ttu-id="537d2-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="537d2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="537d2-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="537d2-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="537d2-110">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="537d2-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="537d2-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="537d2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="537d2-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="537d2-112">See also</span></span>

- [<span data-ttu-id="537d2-113">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="537d2-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
