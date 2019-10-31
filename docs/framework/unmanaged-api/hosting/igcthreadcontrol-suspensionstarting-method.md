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
ms.openlocfilehash: 1e1d63ab28276f69e5b3a762520db8f8300d05bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134759"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="c9fb7-102">IGCThreadControl::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="c9fb7-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="c9fb7-103">Notifica al host que el motor en tiempo de ejecución está iniciando una suspensión de subprocesos para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="c9fb7-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9fb7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9fb7-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="c9fb7-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c9fb7-105">Remarks</span></span>  
 <span data-ttu-id="c9fb7-106">No vuelva a programar ningún subproceso durante la devolución de llamada de `SuspensionStarting`.</span><span class="sxs-lookup"><span data-stu-id="c9fb7-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9fb7-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9fb7-107">Requirements</span></span>  
 <span data-ttu-id="c9fb7-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9fb7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9fb7-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c9fb7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9fb7-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c9fb7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9fb7-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9fb7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9fb7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9fb7-112">See also</span></span>

- [<span data-ttu-id="c9fb7-113">IGCThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9fb7-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
