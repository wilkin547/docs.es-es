---
title: Contenedores COM
description: Los clientes COM y los objetos .NET interactúan mediante un contenedor CCW y un contenedor RCW. CLR crea contenedores automáticamente.
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
ms.openlocfilehash: 17a303cde5fa51cd940b0375d2c6657fcd354dc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706338"
---
# <a name="com-wrappers"></a><span data-ttu-id="ce37c-104">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="ce37c-104">COM Wrappers</span></span>

<span data-ttu-id="ce37c-105">COM se diferencia del modelo de objetos del runtime de .NET en varios aspectos importantes:</span><span class="sxs-lookup"><span data-stu-id="ce37c-105">COM differs from the .NET runtime object model in several important ways:</span></span>  
  
- <span data-ttu-id="ce37c-106">Los clientes de objetos COM deben administrar la duración de los objetos; Common Language Runtime administra la duración de los objetos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="ce37c-106">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
- <span data-ttu-id="ce37c-107">Los clientes de objetos COM detectan si un servicio está disponible solicitando una interfaz que proporciona ese servicio y obteniendo o no un puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="ce37c-107">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="ce37c-108">Los clientes de objetos .NET pueden obtener una descripción de la funcionalidad de un objeto mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="ce37c-108">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
- <span data-ttu-id="ce37c-109">Los objetos .NET residen en memoria administrada por el entorno de ejecución del runtime de .NET.</span><span class="sxs-lookup"><span data-stu-id="ce37c-109">NET objects reside in memory managed by the .NET runtime execution environment.</span></span> <span data-ttu-id="ce37c-110">El entorno de ejecución puede mover los objetos en la memoria por motivos de rendimiento y actualizar todas las referencias a los objetos que mueve.</span><span class="sxs-lookup"><span data-stu-id="ce37c-110">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="ce37c-111">Los clientes no administrados, una vez obtenido un puntero a un objeto, se basan en el objeto para permanecer en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="ce37c-111">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="ce37c-112">Estos clientes no disponen de ningún mecanismo para tratar con un objeto cuya ubicación no es fija.</span><span class="sxs-lookup"><span data-stu-id="ce37c-112">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="ce37c-113">Para superar estas diferencias, el tiempo de ejecución proporciona clases contenedoras para que los clientes administrados y no administrados crean que están llamando a objetos dentro de su propio entorno.</span><span class="sxs-lookup"><span data-stu-id="ce37c-113">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="ce37c-114">Cada vez que un cliente administrado llama a un método en un objeto COM, el tiempo de ejecución crea un [contenedor RCW](runtime-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="ce37c-114">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="ce37c-115">Los contenedores RCW analizan las diferencias entre los mecanismos de referencia administrados y no administrados, entre otras cosas.</span><span class="sxs-lookup"><span data-stu-id="ce37c-115">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="ce37c-116">El tiempo de ejecución crea también un [contenedor CCW](com-callable-wrapper.md) para invertir el proceso, lo que permite a un cliente COM llamar sin problemas a un método en un objeto. NET.</span><span class="sxs-lookup"><span data-stu-id="ce37c-116">The runtime also creates a [COM callable wrapper](com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="ce37c-117">Como se muestra en la ilustración siguiente, la perspectiva del código de llamada determina la clase contenedora que crea el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ce37c-117">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 ![Información general sobre los contenedores COM](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 <span data-ttu-id="ce37c-119">En la mayoría de los casos, el contenedor estándar RCW o CCW generado por el tiempo de ejecución proporciona la serialización adecuada para las llamadas que traspasan los límites entre COM y el runtime de .NET.</span><span class="sxs-lookup"><span data-stu-id="ce37c-119">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET runtime.</span></span> <span data-ttu-id="ce37c-120">Mediante atributos personalizados, puede ajustar el modo en que el tiempo de ejecución representa el código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="ce37c-120">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce37c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce37c-121">See also</span></span>

- <span data-ttu-id="ce37c-122">[Interoperabilidad COM avanzada en .NET Framework](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce37c-122">[Advanced COM Interoperability in .NET Framework](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="ce37c-123">Contenedor al que se puede llamar en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ce37c-123">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
- [<span data-ttu-id="ce37c-124">Contenedor CCW (COM callable wrapper)</span><span class="sxs-lookup"><span data-stu-id="ce37c-124">COM Callable Wrapper</span></span>](com-callable-wrapper.md)
- <span data-ttu-id="ce37c-125">[Personalización de los contenedores estándar en .NET Framework](/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce37c-125">[Customizing Standard Wrappers in .NET Framework](/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span></span>
- <span data-ttu-id="ce37c-126">[Cómo: Personalización de los contenedores RCW en .NET Framework](/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ce37c-126">[How to: Customize Runtime Callable Wrappers in .NET Framework](/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span></span>
