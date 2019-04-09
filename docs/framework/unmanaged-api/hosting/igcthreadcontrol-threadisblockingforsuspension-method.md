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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cd6c1dff30bce8857b9fb4092670667109932c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094091"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="658db-102">IGCThreadControl::ThreadIsBlockingForSuspension (Método)</span><span class="sxs-lookup"><span data-stu-id="658db-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="658db-103">Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="658db-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="658db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="658db-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="658db-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="658db-105">Remarks</span></span>  
 <span data-ttu-id="658db-106">El host puede elegir dentro de la `ThreadIsBlockingForSuspension` devolución de llamada si se debe volver a programar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="658db-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="658db-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="658db-107">Requirements</span></span>  
 <span data-ttu-id="658db-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="658db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="658db-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="658db-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="658db-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="658db-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="658db-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="658db-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="658db-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="658db-112">See also</span></span>

- [<span data-ttu-id="658db-113">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="658db-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
