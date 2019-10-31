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
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140859"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="21769-102">ICLRMetaHostPolicy (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21769-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="21769-103">Proporciona el método [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , que devuelve un puntero a una interfaz Common Language Runtime (CLR) basándose en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="21769-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21769-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="21769-104">Methods</span></span>  
  
|<span data-ttu-id="21769-105">Método</span><span class="sxs-lookup"><span data-stu-id="21769-105">Method</span></span>|<span data-ttu-id="21769-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="21769-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21769-107">GetRequestedRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="21769-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="21769-108">Proporciona una interfaz de CLR preferida basada en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="21769-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21769-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21769-109">Remarks</span></span>  
 <span data-ttu-id="21769-110">Puede obtener una referencia a esta interfaz mediante una llamada a la función [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="21769-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="21769-111">En realidad, esta interfaz no carga ni activa CLR, sino que simplemente devuelve la versión de CLR preferida en función de las versiones disponibles que se instalan o cargan.</span><span class="sxs-lookup"><span data-stu-id="21769-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="21769-112">La API de hospedaje de .NET Framework 4 consolida las directivas para que los hosts con necesidades específicas puedan usar la funcionalidad básica sin incurrir en penalizaciones imprevistas.</span><span class="sxs-lookup"><span data-stu-id="21769-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="21769-113">Por ejemplo, muchas de las exportaciones de MSCorEE. dll se enlazarán a un CLR específico, aunque es posible que un método no lo requiera lógicamente.</span><span class="sxs-lookup"><span data-stu-id="21769-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="21769-114">La enumeración [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) proporciona directivas de enlace que son comunes a la mayoría de los hosts.</span><span class="sxs-lookup"><span data-stu-id="21769-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21769-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21769-115">Requirements</span></span>  
 <span data-ttu-id="21769-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21769-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21769-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="21769-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="21769-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21769-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21769-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21769-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21769-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="21769-120">See also</span></span>

- [<span data-ttu-id="21769-121">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="21769-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="21769-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="21769-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="21769-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="21769-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
