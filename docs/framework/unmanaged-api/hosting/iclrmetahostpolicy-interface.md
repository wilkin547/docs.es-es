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
ms.openlocfilehash: 79b62a5e2aad9cfcd14ba40c1abf0342bfe57a4b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703532"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="a8ba0-102">ICLRMetaHostPolicy (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8ba0-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="a8ba0-103">Proporciona el método [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , que devuelve un puntero a una interfaz Common Language Runtime (CLR) basándose en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a8ba0-103">Provides the [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8ba0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a8ba0-104">Methods</span></span>  
  
|<span data-ttu-id="a8ba0-105">Método</span><span class="sxs-lookup"><span data-stu-id="a8ba0-105">Method</span></span>|<span data-ttu-id="a8ba0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8ba0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8ba0-107">Método GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="a8ba0-107">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="a8ba0-108">Proporciona una interfaz de CLR preferida basada en un criterio de Directiva, un ensamblado administrado, una versión y un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a8ba0-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8ba0-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a8ba0-109">Remarks</span></span>  
 <span data-ttu-id="a8ba0-110">Puede obtener una referencia a esta interfaz mediante una llamada a la función [CLRCreateInstance](clrcreateinstance-function.md) como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8ba0-110">You can get a reference to this interface by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="a8ba0-111">En realidad, esta interfaz no carga ni activa CLR, sino que simplemente devuelve la versión de CLR preferida en función de las versiones disponibles que se instalan o cargan.</span><span class="sxs-lookup"><span data-stu-id="a8ba0-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="a8ba0-112">La API de hospedaje de .NET Framework 4 consolida las directivas para que los hosts con necesidades específicas puedan usar la funcionalidad básica sin incurrir en penalizaciones imprevistas.</span><span class="sxs-lookup"><span data-stu-id="a8ba0-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="a8ba0-113">Por ejemplo, muchas de las exportaciones de MSCorEE. dll se enlazarán a un CLR específico, aunque es posible que un método no lo requiera lógicamente.</span><span class="sxs-lookup"><span data-stu-id="a8ba0-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="a8ba0-114">La enumeración [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) proporciona directivas de enlace que son comunes a la mayoría de los hosts.</span><span class="sxs-lookup"><span data-stu-id="a8ba0-114">The [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8ba0-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8ba0-115">Requirements</span></span>  
 <span data-ttu-id="a8ba0-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8ba0-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ba0-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a8ba0-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a8ba0-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a8ba0-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8ba0-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ba0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ba0-120">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a8ba0-120">See also</span></span>

- [<span data-ttu-id="a8ba0-121">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="a8ba0-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="a8ba0-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a8ba0-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a8ba0-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a8ba0-123">Hosting</span></span>](index.md)
