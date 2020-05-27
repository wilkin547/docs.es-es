---
title: IGCThreadControl::ThreadIsBlockingForSuspension (Método)
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: b5f6d7d40274972438a01313bc6aaec475b8e0c6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805089"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="eb6c7-102">IGCThreadControl::ThreadIsBlockingForSuspension (Método)</span><span class="sxs-lookup"><span data-stu-id="eb6c7-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="eb6c7-103">Notifica al host que el subproceso que está realizando la llamada está a punto de bloquearse, quizás para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="eb6c7-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb6c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb6c7-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="eb6c7-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb6c7-105">Remarks</span></span>  
 <span data-ttu-id="eb6c7-106">El host puede elegir dentro de la `ThreadIsBlockingForSuspension` devolución de llamada si se debe volver a programar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="eb6c7-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb6c7-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb6c7-107">Requirements</span></span>  
 <span data-ttu-id="eb6c7-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb6c7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb6c7-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eb6c7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb6c7-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eb6c7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb6c7-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb6c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb6c7-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb6c7-112">See also</span></span>

- [<span data-ttu-id="eb6c7-113">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb6c7-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
