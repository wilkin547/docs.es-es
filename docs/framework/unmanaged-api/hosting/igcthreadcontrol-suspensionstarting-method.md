---
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
ms.openlocfilehash: 9d39ee79f7734f7dd099a07640ecb06f4f8dcbb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721666"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="17a0c-102">IGCThreadControl::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="17a0c-102">IGCThreadControl::SuspensionStarting Method</span></span>

<span data-ttu-id="17a0c-103">Notifica al host que el motor en tiempo de ejecución está iniciando una suspensión de subprocesos para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="17a0c-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17a0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17a0c-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="17a0c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17a0c-105">Remarks</span></span>  

 <span data-ttu-id="17a0c-106">No vuelva a programar los subprocesos durante la `SuspensionStarting` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="17a0c-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17a0c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17a0c-107">Requirements</span></span>  

 <span data-ttu-id="17a0c-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17a0c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17a0c-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="17a0c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17a0c-110">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17a0c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17a0c-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17a0c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a0c-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17a0c-112">See also</span></span>

- [<span data-ttu-id="17a0c-113">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17a0c-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
