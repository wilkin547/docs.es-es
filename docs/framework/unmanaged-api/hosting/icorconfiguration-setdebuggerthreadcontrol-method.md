---
description: 'Más información sobre: ICorConfiguration:: Setdebuggerthreadcontrol ((método)'
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
ms.openlocfilehash: 9bf024f3feb6df44a94f8a5f1a626bb6e0c91d31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636668"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="e09fb-103">ICorConfiguration::SetDebuggerThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="e09fb-103">ICorConfiguration::SetDebuggerThreadControl Method</span></span>

<span data-ttu-id="e09fb-104">Establece la interfaz de devolución de llamada a la que los servicios de depuración llamarán como subprocesos Common Language Runtime (CLR) se bloquean y desbloquean para la depuración.</span><span class="sxs-lookup"><span data-stu-id="e09fb-104">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e09fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e09fb-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e09fb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e09fb-106">Parameters</span></span>  

 `pDebuggerThreadControl`  
 <span data-ttu-id="e09fb-107">de Un puntero a un objeto [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) que notifica al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="e09fb-107">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e09fb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e09fb-108">Requirements</span></span>  

 <span data-ttu-id="e09fb-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e09fb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e09fb-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e09fb-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e09fb-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e09fb-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e09fb-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e09fb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e09fb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e09fb-113">See also</span></span>

- [<span data-ttu-id="e09fb-114">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e09fb-114">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
