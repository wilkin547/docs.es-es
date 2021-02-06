---
description: 'Más información acerca de: ICLRMetaHostPolicy (interfaz)'
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
ms.openlocfilehash: b14ad417617c32242f8a59844f7c1f1a8d05c78d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637422"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="e1060-103">ICLRMetaHostPolicy (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1060-103">ICLRMetaHostPolicy Interface</span></span>

<span data-ttu-id="e1060-104">Proporciona el método [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , que devuelve un puntero a una interfaz Common Language Runtime (CLR) basándose en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e1060-104">Provides the [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1060-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e1060-105">Methods</span></span>  
  
|<span data-ttu-id="e1060-106">Método</span><span class="sxs-lookup"><span data-stu-id="e1060-106">Method</span></span>|<span data-ttu-id="e1060-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1060-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1060-108">Método GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="e1060-108">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="e1060-109">Proporciona una interfaz de CLR preferida basada en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e1060-109">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1060-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e1060-110">Remarks</span></span>  

 <span data-ttu-id="e1060-111">Puede obtener una referencia a esta interfaz mediante una llamada a la función [CLRCreateInstance](clrcreateinstance-function.md) como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1060-111">You can get a reference to this interface by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="e1060-112">En realidad, esta interfaz no carga ni activa CLR, sino que simplemente devuelve la versión de CLR preferida en función de las versiones disponibles que se instalan o cargan.</span><span class="sxs-lookup"><span data-stu-id="e1060-112">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="e1060-113">La API de hospedaje de .NET Framework 4 consolida las directivas para que los hosts con necesidades específicas puedan usar la funcionalidad básica sin incurrir en penalizaciones imprevistas.</span><span class="sxs-lookup"><span data-stu-id="e1060-113">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="e1060-114">Por ejemplo, muchas de las exportaciones de MSCorEE.dll se enlazarán a un CLR específico, aunque es posible que un método no lo requiera lógicamente.</span><span class="sxs-lookup"><span data-stu-id="e1060-114">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="e1060-115">La enumeración [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) proporciona directivas de enlace que son comunes a la mayoría de los hosts.</span><span class="sxs-lookup"><span data-stu-id="e1060-115">The [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1060-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1060-116">Requirements</span></span>  

 <span data-ttu-id="e1060-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1060-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1060-118">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e1060-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1060-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1060-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1060-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1060-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1060-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1060-121">See also</span></span>

- [<span data-ttu-id="e1060-122">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="e1060-122">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="e1060-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e1060-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e1060-124">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e1060-124">Hosting</span></span>](index.md)
