---
title: ICLRMetaHostPolicy (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93507ac72b79210dc3a267fea39a6a7b2874916a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188576"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="19dc2-102">ICLRMetaHostPolicy (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19dc2-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="19dc2-103">Proporciona el [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) administrado de método, que devuelve un puntero a una interfaz de common language runtime (CLR) basándose en criterios de directiva, un archivo de ensamblado, versión y configuración.</span><span class="sxs-lookup"><span data-stu-id="19dc2-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19dc2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="19dc2-104">Methods</span></span>  
  
|<span data-ttu-id="19dc2-105">Método</span><span class="sxs-lookup"><span data-stu-id="19dc2-105">Method</span></span>|<span data-ttu-id="19dc2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="19dc2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19dc2-107">GetRequestedRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="19dc2-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="19dc2-108">Proporciona una interfaz CLR preferida basándose en criterios de directiva, administrado un archivo de ensamblado, versión y la configuración.</span><span class="sxs-lookup"><span data-stu-id="19dc2-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19dc2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19dc2-109">Remarks</span></span>  
 <span data-ttu-id="19dc2-110">Puede obtener una referencia a esta interfaz mediante una llamada a la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funcione como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="19dc2-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="19dc2-111">Esta interfaz realmente no carga ni activa el CLR, sino que simplemente devuelve la versión CLR preferida en función de las versiones disponibles que están instaladas o cargadas.</span><span class="sxs-lookup"><span data-stu-id="19dc2-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="19dc2-112">El [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API de hospedaje consolida las directivas para que los hosts con necesidades concretas pueden usar la funcionalidad básica sin incurrir en penalizaciones imprevistas.</span><span class="sxs-lookup"><span data-stu-id="19dc2-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="19dc2-113">Por ejemplo, muchas de las exportaciones de MSCorEE.dll se enlazará a un CLR concreto, aunque un método no es posible que lo necesite lógicamente.</span><span class="sxs-lookup"><span data-stu-id="19dc2-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="19dc2-114">El [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeración proporciona directivas de enlace que son comunes a la mayoría de los hosts.</span><span class="sxs-lookup"><span data-stu-id="19dc2-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19dc2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19dc2-115">Requirements</span></span>  
 <span data-ttu-id="19dc2-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19dc2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19dc2-117">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="19dc2-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="19dc2-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19dc2-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19dc2-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19dc2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19dc2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="19dc2-120">See also</span></span>

- [<span data-ttu-id="19dc2-121">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="19dc2-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="19dc2-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="19dc2-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="19dc2-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="19dc2-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
