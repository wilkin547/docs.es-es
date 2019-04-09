---
title: ICorConfiguration::SetGCThreadControl (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b50c87efeb8ad2311a75886da677a9dc901bca1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135842"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="ac110-102">ICorConfiguration::SetGCThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="ac110-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="ac110-103">Establece la interfaz de devolución de llamada para la programación de subprocesos para tareas que no son de tiempo de ejecución que de lo contrario, se bloquearía para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ac110-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac110-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac110-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac110-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac110-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="ac110-106">[in] Un puntero a un [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) objeto que notifica al host la suspensión de subprocesos para tareas que no son de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac110-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac110-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac110-107">Remarks</span></span>  
 <span data-ttu-id="ac110-108">El host puede elegir dentro de la [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) devolución de llamada si se debe volver a programar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="ac110-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac110-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac110-109">Requirements</span></span>  
 <span data-ttu-id="ac110-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac110-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac110-111">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac110-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac110-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac110-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ac110-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ac110-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ac110-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac110-114">See also</span></span>

- [<span data-ttu-id="ac110-115">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac110-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
