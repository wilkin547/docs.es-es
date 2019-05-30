---
title: IGCHost (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 167e2477e5185112408793e145bc5a4fabea7fc8
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377615"
---
# <a name="igchost-interface"></a><span data-ttu-id="81102-102">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81102-102">IGCHost Interface</span></span>
<span data-ttu-id="81102-103">Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="81102-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81102-104">A partir de .NET Framework 4.5, puede usar el [Igchost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método para establecer el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados en los valores de mayor que el `DWORD` límite impuesto por el [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="81102-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81102-105">Esta interfaz es para experto uso exclusivo.</span><span class="sxs-lookup"><span data-stu-id="81102-105">This interface is for expert usage only.</span></span> <span data-ttu-id="81102-106">Si se utiliza incorrectamente puede afectar al rendimiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="81102-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81102-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="81102-107">Methods</span></span>  
  
|<span data-ttu-id="81102-108">Método</span><span class="sxs-lookup"><span data-stu-id="81102-108">Method</span></span>|<span data-ttu-id="81102-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="81102-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81102-110">Collect (método)</span><span class="sxs-lookup"><span data-stu-id="81102-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="81102-111">Fuerza una recolección que se produzca la generación determinada, independientemente del estado de la recolección de elementos actual.</span><span class="sxs-lookup"><span data-stu-id="81102-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="81102-112">GetStats (método)</span><span class="sxs-lookup"><span data-stu-id="81102-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="81102-113">Obtiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="81102-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="81102-114">GetThreadStats (método)</span><span class="sxs-lookup"><span data-stu-id="81102-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="81102-115">Obtiene las estadísticas por subproceso para la recolección.</span><span class="sxs-lookup"><span data-stu-id="81102-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="81102-116">SetGCStartupLimits (método)</span><span class="sxs-lookup"><span data-stu-id="81102-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="81102-117">Establece el tamaño del segmento y el tamaño máximo para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="81102-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="81102-118">SetVirtualMemLimit (método)</span><span class="sxs-lookup"><span data-stu-id="81102-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="81102-119">Establece el tamaño máximo de memoria virtual de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="81102-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81102-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81102-120">Requirements</span></span>  
 <span data-ttu-id="81102-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81102-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81102-122">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="81102-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="81102-123">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81102-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81102-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81102-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81102-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="81102-125">See also</span></span>

- [<span data-ttu-id="81102-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="81102-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="81102-127">CorRuntimeHost (coclase)</span><span class="sxs-lookup"><span data-stu-id="81102-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
