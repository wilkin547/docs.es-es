---
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
ms.openlocfilehash: f7cdc3fe9d52db56d0280bc602d3a9f2f54e8246
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805250"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="68910-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="68910-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="68910-103">Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="68910-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68910-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68910-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="68910-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="68910-105">Remarks</span></span>  
 <span data-ttu-id="68910-106">`ThreadIsBlockingForDebugger`Siempre se llamará al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="68910-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="68910-107">El `ThreadIsBlockingForDebugger` método proporciona al host una oportunidad para realizar otra acción mientras el subproceso se bloquea.</span><span class="sxs-lookup"><span data-stu-id="68910-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68910-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68910-108">Requirements</span></span>  
 <span data-ttu-id="68910-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68910-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68910-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="68910-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68910-111">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="68910-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68910-112">**Versiones de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68910-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68910-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68910-113">See also</span></span>

- [<span data-ttu-id="68910-114">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="68910-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
