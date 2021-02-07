---
description: 'Más información acerca de: interfaz IGCHost'
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
ms.openlocfilehash: 73b1125eb66a38373da85769ab80ddcaf0b955c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709599"
---
# <a name="igchost-interface"></a><span data-ttu-id="ed94a-103">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed94a-103">IGCHost Interface</span></span>

<span data-ttu-id="ed94a-104">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ed94a-104">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed94a-105">A partir del .NET Framework 4,5, puede usar el método [igchost2 (:: setgcstartuplimitsex (](igchost2-setgcstartuplimitsex-method.md) para establecer el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados en valores mayores que el `DWORD` límite impuesto por el método [setgcstartuplimits (](igchost-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ed94a-105">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed94a-106">Esta interfaz solo es para uso experto.</span><span class="sxs-lookup"><span data-stu-id="ed94a-106">This interface is for expert usage only.</span></span> <span data-ttu-id="ed94a-107">Puede afectar al rendimiento de una aplicación si se usa de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="ed94a-107">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed94a-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="ed94a-108">Methods</span></span>  
  
|<span data-ttu-id="ed94a-109">Método</span><span class="sxs-lookup"><span data-stu-id="ed94a-109">Method</span></span>|<span data-ttu-id="ed94a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed94a-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed94a-111">Método Collect</span><span class="sxs-lookup"><span data-stu-id="ed94a-111">Collect Method</span></span>](igchost-collect-method.md)|<span data-ttu-id="ed94a-112">Obliga a que se produzca una colección para la generación dada, independientemente del estado de la recolección de elementos no utilizados actual.</span><span class="sxs-lookup"><span data-stu-id="ed94a-112">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="ed94a-113">GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="ed94a-113">GetStats Method</span></span>](igchost-getstats-method.md)|<span data-ttu-id="ed94a-114">Obtiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ed94a-114">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="ed94a-115">Método GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="ed94a-115">GetThreadStats Method</span></span>](igchost-getthreadstats-method.md)|<span data-ttu-id="ed94a-116">Obtiene las estadísticas por subproceso para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ed94a-116">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="ed94a-117">Método SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="ed94a-117">SetGCStartupLimits Method</span></span>](igchost-setgcstartuplimits-method.md)|<span data-ttu-id="ed94a-118">Establece el tamaño del segmento y el tamaño máximo de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="ed94a-118">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="ed94a-119">Método SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="ed94a-119">SetVirtualMemLimit Method</span></span>](igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="ed94a-120">Establece el tamaño máximo de la memoria virtual del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed94a-120">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed94a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed94a-121">Requirements</span></span>  

 <span data-ttu-id="ed94a-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed94a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed94a-123">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="ed94a-123">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ed94a-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed94a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed94a-125">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed94a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed94a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed94a-126">See also</span></span>

- [<span data-ttu-id="ed94a-127">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ed94a-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="ed94a-128">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="ed94a-128">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
