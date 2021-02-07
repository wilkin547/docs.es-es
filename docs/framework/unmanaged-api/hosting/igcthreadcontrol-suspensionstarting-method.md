---
description: 'Más información sobre: IGCThreadControl:: SuspensionStarting ((método)'
title: IGCThreadControl::SuspensionStarting (Método)
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: b9d068e6995a73e9a9a31d5d5debf008f9748630
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709301"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="6e7c5-103">IGCThreadControl::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="6e7c5-103">IGCThreadControl::SuspensionStarting Method</span></span>

<span data-ttu-id="6e7c5-104">Notifica al host que el motor en tiempo de ejecución está iniciando una suspensión de subprocesos para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="6e7c5-104">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e7c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e7c5-105">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e7c5-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6e7c5-106">Remarks</span></span>  

 <span data-ttu-id="6e7c5-107">No vuelva a programar los subprocesos durante la `SuspensionStarting` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6e7c5-107">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e7c5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e7c5-108">Requirements</span></span>  

 <span data-ttu-id="6e7c5-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e7c5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e7c5-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6e7c5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e7c5-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e7c5-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e7c5-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e7c5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e7c5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e7c5-113">See also</span></span>

- [<span data-ttu-id="6e7c5-114">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e7c5-114">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
