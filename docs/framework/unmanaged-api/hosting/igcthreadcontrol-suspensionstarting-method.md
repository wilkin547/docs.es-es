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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7613bc744ad4c2e172fc4f6dd7bf282fb3d9072c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179756"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="33384-102">IGCThreadControl::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="33384-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="33384-103">Notifica al host que el tiempo de ejecución está iniciando la suspensión de un subproceso para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="33384-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33384-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33384-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="33384-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33384-105">Remarks</span></span>  
 <span data-ttu-id="33384-106">No volver a programar los subprocesos durante la `SuspensionStarting` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="33384-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33384-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33384-107">Requirements</span></span>  
 <span data-ttu-id="33384-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33384-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33384-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33384-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33384-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33384-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="33384-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="33384-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="33384-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="33384-112">See also</span></span>

- [<span data-ttu-id="33384-113">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33384-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
