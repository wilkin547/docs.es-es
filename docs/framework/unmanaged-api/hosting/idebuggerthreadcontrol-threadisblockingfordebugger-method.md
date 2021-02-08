---
description: 'Más información sobre: IDebuggerThreadControl:: ThreadIsBlockingForDebugger ((método)'
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
ms.openlocfilehash: 0fa96b2e36ea6653e1698dd32fa1e73d223afb94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789520"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="eaf27-103">IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="eaf27-103">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>

<span data-ttu-id="eaf27-104">Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="eaf27-104">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf27-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eaf27-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="eaf27-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eaf27-106">Remarks</span></span>  

 <span data-ttu-id="eaf27-107">`ThreadIsBlockingForDebugger`Siempre se llamará al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="eaf27-107">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="eaf27-108">El `ThreadIsBlockingForDebugger` método proporciona al host una oportunidad para realizar otra acción mientras el subproceso se bloquea.</span><span class="sxs-lookup"><span data-stu-id="eaf27-108">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaf27-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eaf27-109">Requirements</span></span>  

 <span data-ttu-id="eaf27-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaf27-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf27-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eaf27-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eaf27-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eaf27-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eaf27-113">**Versiones de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf27-113">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf27-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="eaf27-114">See also</span></span>

- [<span data-ttu-id="eaf27-115">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eaf27-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
