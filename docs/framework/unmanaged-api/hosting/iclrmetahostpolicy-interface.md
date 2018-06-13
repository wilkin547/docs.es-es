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
ms.openlocfilehash: f9a70cf0812f84908630f109ef06aafa4b4f7525
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434427"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="ffe76-102">ICLRMetaHostPolicy (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffe76-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="ffe76-103">Proporciona el [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) administrado de método, que devuelve un puntero a una interfaz de common language runtime (CLR) basándose en criterios de directiva, un archivo de ensamblado, la versión y la configuración.</span><span class="sxs-lookup"><span data-stu-id="ffe76-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffe76-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ffe76-104">Methods</span></span>  
  
|<span data-ttu-id="ffe76-105">Método</span><span class="sxs-lookup"><span data-stu-id="ffe76-105">Method</span></span>|<span data-ttu-id="ffe76-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffe76-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffe76-107">GetRequestedRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="ffe76-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="ffe76-108">Proporciona una interfaz CLR preferida basándose en criterios de la directiva, administrado un archivo de ensamblado, la versión y la configuración.</span><span class="sxs-lookup"><span data-stu-id="ffe76-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffe76-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ffe76-109">Remarks</span></span>  
 <span data-ttu-id="ffe76-110">Puede obtener una referencia a esta interfaz mediante una llamada a la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funcione como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffe76-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="ffe76-111">Esta interfaz realmente no carga ni activa el CLR, sino que simplemente devuelve la versión CLR preferida basándose en las versiones disponibles que están instaladas o cargadas.</span><span class="sxs-lookup"><span data-stu-id="ffe76-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="ffe76-112">El [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API de hospedaje consolida las directivas para que los hosts con necesidades específicas pueden utilizar la funcionalidad básica sin incurrir en penalizaciones imprevistas.</span><span class="sxs-lookup"><span data-stu-id="ffe76-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="ffe76-113">Por ejemplo, muchas de las exportaciones de MSCorEE.dll se enlazará a un CLR concreto, aunque un método no lo necesite lógicamente.</span><span class="sxs-lookup"><span data-stu-id="ffe76-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="ffe76-114">El [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeración proporciona directivas de enlace que son comunes a la mayoría de los hosts.</span><span class="sxs-lookup"><span data-stu-id="ffe76-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffe76-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ffe76-115">Requirements</span></span>  
 <span data-ttu-id="ffe76-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffe76-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffe76-117">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ffe76-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ffe76-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffe76-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffe76-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffe76-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe76-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffe76-120">See Also</span></span>  
 [<span data-ttu-id="ffe76-121">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="ffe76-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="ffe76-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ffe76-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="ffe76-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ffe76-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
