---
title: "IGCThreadControl::ThreadIsBlockingForSuspension (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.ThreadIsBlockingForSuspension
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 815ed06cb5772e7d04002f9d0d31bd971f2d345a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="db4e0-102">IGCThreadControl::ThreadIsBlockingForSuspension (Método)</span><span class="sxs-lookup"><span data-stu-id="db4e0-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="db4e0-103">Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="db4e0-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db4e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db4e0-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="db4e0-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db4e0-105">Remarks</span></span>  
 <span data-ttu-id="db4e0-106">El host puede elegir dentro de la `ThreadIsBlockingForSuspension` devolución de llamada si se debe volver a programar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="db4e0-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db4e0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db4e0-107">Requirements</span></span>  
 <span data-ttu-id="db4e0-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db4e0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db4e0-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db4e0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db4e0-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db4e0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db4e0-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db4e0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db4e0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="db4e0-112">See Also</span></span>  
 [<span data-ttu-id="db4e0-113">IGCThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db4e0-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
