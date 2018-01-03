---
title: Contenedores COM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb84ce5bec2808b0149a5ca44b05a9c99143d580
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="com-wrappers"></a><span data-ttu-id="3649d-102">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="3649d-102">COM Wrappers</span></span>
<span data-ttu-id="3649d-103">COM se diferencia del modelo de objetos de .NET Framework en varios aspectos importantes:</span><span class="sxs-lookup"><span data-stu-id="3649d-103">COM differs from the .NET Framework object model in several important ways:</span></span>  
  
-   <span data-ttu-id="3649d-104">Los clientes de objetos COM deben administrar la duración de los objetos; Common Language Runtime administra la duración de los objetos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="3649d-104">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
-   <span data-ttu-id="3649d-105">Los clientes de objetos COM detectan si un servicio está disponible solicitando una interfaz que proporciona ese servicio y obteniendo o no un puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="3649d-105">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="3649d-106">Los clientes de objetos .NET pueden obtener una descripción de la funcionalidad de un objeto mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="3649d-106">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
-   <span data-ttu-id="3649d-107">Los objetos .NET residen en memoria administrada por el entorno de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3649d-107">NET objects reside in memory managed by the .NET Framework execution environment.</span></span> <span data-ttu-id="3649d-108">El entorno de ejecución puede mover los objetos en la memoria por motivos de rendimiento y actualizar todas las referencias a los objetos que mueve.</span><span class="sxs-lookup"><span data-stu-id="3649d-108">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="3649d-109">Los clientes no administrados, una vez obtenido un puntero a un objeto, se basan en el objeto para permanecer en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="3649d-109">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="3649d-110">Estos clientes no disponen de ningún mecanismo para tratar con un objeto cuya ubicación no es fija.</span><span class="sxs-lookup"><span data-stu-id="3649d-110">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="3649d-111">Para superar estas diferencias, el tiempo de ejecución proporciona clases contenedoras para que los clientes administrados y no administrados crean que están llamando a objetos dentro de su propio entorno.</span><span class="sxs-lookup"><span data-stu-id="3649d-111">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="3649d-112">Cada vez que un cliente administrado llama a un método en un objeto COM, el tiempo de ejecución crea un [contenedor RCW](../../../docs/framework/interop/runtime-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="3649d-112">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="3649d-113">Los contenedores RCW analizan las diferencias entre los mecanismos de referencia administrados y no administrados, entre otras cosas.</span><span class="sxs-lookup"><span data-stu-id="3649d-113">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="3649d-114">El tiempo de ejecución crea también un [contenedor CCW](../../../docs/framework/interop/com-callable-wrapper.md) para invertir el proceso, lo que permite a un cliente COM llamar sin problemas a un método en un objeto. NET.</span><span class="sxs-lookup"><span data-stu-id="3649d-114">The runtime also creates a [COM callable wrapper](../../../docs/framework/interop/com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="3649d-115">Como se muestra en la ilustración siguiente, la perspectiva del código de llamada determina la clase contenedora que crea el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3649d-115">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 <span data-ttu-id="3649d-116">![Información general sobre los contenedores COM](../../../docs/framework/interop/media/bidirectional.gif "bidireccional")</span><span class="sxs-lookup"><span data-stu-id="3649d-116">![COM wrapper overview](../../../docs/framework/interop/media/bidirectional.gif "bidirectional")</span></span>  
<span data-ttu-id="3649d-117">Información general sobre los contenedores COM</span><span class="sxs-lookup"><span data-stu-id="3649d-117">COM wrapper overview</span></span>  
  
 <span data-ttu-id="3649d-118">En la mayoría de los casos, el contenedor estándar RCW o CCW generado por el tiempo de ejecución proporciona la serialización adecuada para las llamadas que traspasan los límites entre COM y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3649d-118">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET Framework.</span></span> <span data-ttu-id="3649d-119">Mediante atributos personalizados, puede ajustar el modo en que el tiempo de ejecución representa el código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="3649d-119">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3649d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3649d-120">See Also</span></span>  
 [<span data-ttu-id="3649d-121">Interoperabilidad COM avanzada</span><span class="sxs-lookup"><span data-stu-id="3649d-121">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="3649d-122">Contenedor al que se puede llamar en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3649d-122">Runtime Callable Wrapper</span></span>](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [<span data-ttu-id="3649d-123">Contenedor CCW (COM callable wrapper)</span><span class="sxs-lookup"><span data-stu-id="3649d-123">COM Callable Wrapper</span></span>](../../../docs/framework/interop/com-callable-wrapper.md)  
 [<span data-ttu-id="3649d-124">Personalizar contenedores estándar</span><span class="sxs-lookup"><span data-stu-id="3649d-124">Customizing Standard Wrappers</span></span>](http://msdn.microsoft.com/en-us/c40d089b-6a3c-41b5-a20d-d760c215e49d)  
 [<span data-ttu-id="3649d-125">Cómo: Personalizar contenedores RCW</span><span class="sxs-lookup"><span data-stu-id="3649d-125">How to: Customize Runtime Callable Wrappers</span></span>](http://msdn.microsoft.com/en-us/4a4bb3da-4d60-4517-99f2-78d46a681732)
