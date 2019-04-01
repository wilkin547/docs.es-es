---
title: Contenedores COM
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce15e0535bbd6bc67054c651a518f11cf9dd2ae1
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410360"
---
# <a name="com-wrappers"></a><span data-ttu-id="bf6f8-102">Contenedores COM</span><span class="sxs-lookup"><span data-stu-id="bf6f8-102">COM Wrappers</span></span>
<span data-ttu-id="bf6f8-103">COM se diferencia del modelo de objetos de .NET Framework en varios aspectos importantes:</span><span class="sxs-lookup"><span data-stu-id="bf6f8-103">COM differs from the .NET Framework object model in several important ways:</span></span>  
  
-   <span data-ttu-id="bf6f8-104">Los clientes de objetos COM deben administrar la duración de los objetos; Common Language Runtime administra la duración de los objetos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-104">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
-   <span data-ttu-id="bf6f8-105">Los clientes de objetos COM detectan si un servicio está disponible solicitando una interfaz que proporciona ese servicio y obteniendo o no un puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-105">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="bf6f8-106">Los clientes de objetos .NET pueden obtener una descripción de la funcionalidad de un objeto mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-106">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
-   <span data-ttu-id="bf6f8-107">Los objetos .NET residen en memoria administrada por el entorno de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-107">NET objects reside in memory managed by the .NET Framework execution environment.</span></span> <span data-ttu-id="bf6f8-108">El entorno de ejecución puede mover los objetos en la memoria por motivos de rendimiento y actualizar todas las referencias a los objetos que mueve.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-108">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="bf6f8-109">Los clientes no administrados, una vez obtenido un puntero a un objeto, se basan en el objeto para permanecer en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-109">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="bf6f8-110">Estos clientes no disponen de ningún mecanismo para tratar con un objeto cuya ubicación no es fija.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-110">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="bf6f8-111">Para superar estas diferencias, el tiempo de ejecución proporciona clases contenedoras para que los clientes administrados y no administrados crean que están llamando a objetos dentro de su propio entorno.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-111">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="bf6f8-112">Cada vez que un cliente administrado llama a un método en un objeto COM, el tiempo de ejecución crea un [contenedor RCW](runtime-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="bf6f8-112">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="bf6f8-113">Los contenedores RCW analizan las diferencias entre los mecanismos de referencia administrados y no administrados, entre otras cosas.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-113">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="bf6f8-114">El tiempo de ejecución crea también un [contenedor CCW](com-callable-wrapper.md) para invertir el proceso, lo que permite a un cliente COM llamar sin problemas a un método en un objeto. NET.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-114">The runtime also creates a [COM callable wrapper](com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="bf6f8-115">Como se muestra en la ilustración siguiente, la perspectiva del código de llamada determina la clase contenedora que crea el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-115">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 ![Información general sobre los contenedores COM](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 <span data-ttu-id="bf6f8-117">En la mayoría de los casos, el contenedor estándar RCW o CCW generado por el tiempo de ejecución proporciona la serialización adecuada para las llamadas que traspasan los límites entre COM y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-117">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET Framework.</span></span> <span data-ttu-id="bf6f8-118">Mediante atributos personalizados, puede ajustar el modo en que el tiempo de ejecución representa el código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="bf6f8-118">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6f8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf6f8-119">See also</span></span>
- <span data-ttu-id="bf6f8-120">[Interoperabilidad COM avanzada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bf6f8-120">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="bf6f8-121">Contenedor al que se puede llamar en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bf6f8-121">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
- [<span data-ttu-id="bf6f8-122">Contenedor CCW (COM callable wrapper)</span><span class="sxs-lookup"><span data-stu-id="bf6f8-122">COM Callable Wrapper</span></span>](com-callable-wrapper.md)
- <span data-ttu-id="bf6f8-123">[Personalización de contenedores estándar](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bf6f8-123">[Customizing Standard Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span></span>
- <span data-ttu-id="bf6f8-124">[Cómo: Personalizar contenedores RCW](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bf6f8-124">[How to: Customize Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span></span>
