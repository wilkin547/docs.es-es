---
title: Clases COM de ejemplo (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: 2dd1092d9c1f6bb7482c306339a3d7f6684940eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322280"
---
# <a name="example-com-class-c-programming-guide"></a><span data-ttu-id="ce9c4-102">Clases COM de ejemplo (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ce9c4-102">Example COM Class (C# Programming Guide)</span></span>
<span data-ttu-id="ce9c4-103">El siguiente es un ejemplo de una clase que se expondría como un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-103">The following is an example of a class that you would expose as a COM object.</span></span> <span data-ttu-id="ce9c4-104">Una vez insertado este código de ejemplo en un archivo .cs y agregado al proyecto, establezca la propiedad **Registrar para interoperabilidad COM** en **True**.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-104">After this code has been placed in a .cs file and added to your project, set the **Register for COM Interop** property to **True**.</span></span> <span data-ttu-id="ce9c4-105">Para obtener más información, vea [NIB: Cómo: Registrar un componente para interoperabilidad COM](http://msdn.microsoft.com/library/4de7d474-56e8-4027-994d-d47ca4725c5e).</span><span class="sxs-lookup"><span data-stu-id="ce9c4-105">For more information, see [NIB: How to: Register a Component for COM Interop](http://msdn.microsoft.com/library/4de7d474-56e8-4027-994d-d47ca4725c5e).</span></span>  
  
 <span data-ttu-id="ce9c4-106">Exponer objetos de Visual C# para COM requiere declarar una interfaz de clase, una interfaz de eventos si es necesario y la propia clase.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-106">Exposing Visual C# objects to COM requires declaring a class interface, an events interface if it is required, and the class itself.</span></span> <span data-ttu-id="ce9c4-107">Los miembros de clase deben seguir estas reglas para que sean visibles en COM:</span><span class="sxs-lookup"><span data-stu-id="ce9c4-107">Class members must follow these rules to be visible to COM:</span></span>  
  
-   <span data-ttu-id="ce9c4-108">La clase debe ser pública.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-108">The class must be public.</span></span>  
  
-   <span data-ttu-id="ce9c4-109">Las propiedades, métodos y eventos deben ser públicos.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-109">Properties, methods, and events must be public.</span></span>  
  
-   <span data-ttu-id="ce9c4-110">Las propiedades y métodos deben declararse en la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-110">Properties and methods must be declared on the class interface.</span></span>  
  
-   <span data-ttu-id="ce9c4-111">Los eventos deben declararse en la interfaz de eventos.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-111">Events must be declared in the event interface.</span></span>  
  
 <span data-ttu-id="ce9c4-112">Los demás miembros públicos de la clase que no se declaren en estas interfaces no serán visibles para COM, pero lo serán para el resto de objetos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-112">Other public members in the class that are not declared in these interfaces will not be visible to COM, but they will be visible to other .NET Framework objects.</span></span>  
  
 <span data-ttu-id="ce9c4-113">Para exponer propiedades y métodos en COM, se deben declarar en la interfaz de clase y marcar con el atributo `DispId`, e implementarlos en la clase.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-113">To expose properties and methods to COM, you must declare them on the class interface and mark them with a `DispId` attribute, and implement them in the class.</span></span> <span data-ttu-id="ce9c4-114">El orden en que se declaran los miembros en la interfaz es el orden usado para la tabla virtual de COM.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-114">The order in which the members are declared in the interface is the order used for the COM vtable.</span></span>  
  
 <span data-ttu-id="ce9c4-115">Para exponer los eventos de la clase, se deben declarar en la interfaz de eventos y marcarlos con un atributo `DispId`.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-115">To expose events from your class, you must declare them on the events interface and mark them with a `DispId` attribute.</span></span> <span data-ttu-id="ce9c4-116">La clase no debe implementar esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-116">The class should not implement this interface.</span></span>  
  
 <span data-ttu-id="ce9c4-117">La clase implementa la interfaz de clase y puede implementar más de una interfaz, pero la primera implementación debe ser la interfaz de clase predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-117">The class implements the class interface; it can implement more than one interface, but the first implementation will be the default class interface.</span></span> <span data-ttu-id="ce9c4-118">Implemente los métodos y propiedades expuestos para COM aquí.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-118">Implement the methods and properties exposed to COM here.</span></span> <span data-ttu-id="ce9c4-119">Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-119">They must be marked public and must match the declarations in the class interface.</span></span> <span data-ttu-id="ce9c4-120">Asimismo, declare los eventos iniciados por la clase aquí.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-120">Also, declare the events raised by the class here.</span></span> <span data-ttu-id="ce9c4-121">Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de eventos.</span><span class="sxs-lookup"><span data-stu-id="ce9c4-121">They must be marked public and must match the declarations in the events interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce9c4-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce9c4-122">Example</span></span>  
 [!code-csharp[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/example-com-class_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ce9c4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce9c4-123">See Also</span></span>  
 [<span data-ttu-id="ce9c4-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ce9c4-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ce9c4-125">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="ce9c4-125">Interoperability</span></span>](../../../csharp/programming-guide/interop/index.md)  
 [<span data-ttu-id="ce9c4-126">Página Compilar (Diseñador de proyectos) (C#)</span><span class="sxs-lookup"><span data-stu-id="ce9c4-126">Build Page, Project Designer (C#)</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)
