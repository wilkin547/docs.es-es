---
title: 'Clase COM de ejemplo: Guía de programación de C#'
description: Aprenda a exponer una clase como un objeto COM en C#. En este ejemplo se agrega código de un archivo .cs a un proyecto y se establece la propiedad Registrar para interoperabilidad COM.
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: d49d391f5ea7717e0c36782be65cfb2ae154b843
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542801"
---
# <a name="example-com-class-c-programming-guide"></a><span data-ttu-id="f0c88-104">Clases COM de ejemplo (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f0c88-104">Example COM Class (C# Programming Guide)</span></span>
<span data-ttu-id="f0c88-105">El siguiente es un ejemplo de una clase que se expondría como un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="f0c88-105">The following is an example of a class that you would expose as a COM object.</span></span> <span data-ttu-id="f0c88-106">Una vez insertado este código de ejemplo en un archivo .cs y agregado al proyecto, establezca la propiedad **Registrar para interoperabilidad COM** en **True**.</span><span class="sxs-lookup"><span data-stu-id="f0c88-106">After this code has been placed in a .cs file and added to your project, set the **Register for COM Interop** property to **True**.</span></span> <span data-ttu-id="f0c88-107">Para obtener más información, vea [Cómo: Registrar un componente para interoperabilidad COM](/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f0c88-107">For more information, see [How to: Register a Component for COM Interop](/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).</span></span>
  
 <span data-ttu-id="f0c88-108">Exponer objetos de Visual C# para COM requiere declarar una interfaz de clase, una interfaz de eventos si es necesario y la propia clase.</span><span class="sxs-lookup"><span data-stu-id="f0c88-108">Exposing Visual C# objects to COM requires declaring a class interface, an events interface if it is required, and the class itself.</span></span> <span data-ttu-id="f0c88-109">Los miembros de clase deben seguir estas reglas para que sean visibles en COM:</span><span class="sxs-lookup"><span data-stu-id="f0c88-109">Class members must follow these rules to be visible to COM:</span></span>  
  
- <span data-ttu-id="f0c88-110">La clase debe ser pública.</span><span class="sxs-lookup"><span data-stu-id="f0c88-110">The class must be public.</span></span>  
  
- <span data-ttu-id="f0c88-111">Las propiedades, métodos y eventos deben ser públicos.</span><span class="sxs-lookup"><span data-stu-id="f0c88-111">Properties, methods, and events must be public.</span></span>  
  
- <span data-ttu-id="f0c88-112">Las propiedades y métodos deben declararse en la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="f0c88-112">Properties and methods must be declared on the class interface.</span></span>  
  
- <span data-ttu-id="f0c88-113">Los eventos deben declararse en la interfaz de eventos.</span><span class="sxs-lookup"><span data-stu-id="f0c88-113">Events must be declared in the event interface.</span></span>  
  
 <span data-ttu-id="f0c88-114">Los demás miembros públicos de la clase que no se declaren en estas interfaces no serán visibles para COM, pero lo serán para el resto de objetos de .NET.</span><span class="sxs-lookup"><span data-stu-id="f0c88-114">Other public members in the class that are not declared in these interfaces will not be visible to COM, but they will be visible to other .NET objects.</span></span>  
  
 <span data-ttu-id="f0c88-115">Para exponer propiedades y métodos en COM, se deben declarar en la interfaz de clase y marcar con el atributo `DispId`, e implementarlos en la clase.</span><span class="sxs-lookup"><span data-stu-id="f0c88-115">To expose properties and methods to COM, you must declare them on the class interface and mark them with a `DispId` attribute, and implement them in the class.</span></span> <span data-ttu-id="f0c88-116">El orden en que se declaran los miembros en la interfaz es el orden usado para la tabla virtual de COM.</span><span class="sxs-lookup"><span data-stu-id="f0c88-116">The order in which the members are declared in the interface is the order used for the COM vtable.</span></span>  
  
 <span data-ttu-id="f0c88-117">Para exponer los eventos de la clase, se deben declarar en la interfaz de eventos y marcarlos con un atributo `DispId`.</span><span class="sxs-lookup"><span data-stu-id="f0c88-117">To expose events from your class, you must declare them on the events interface and mark them with a `DispId` attribute.</span></span> <span data-ttu-id="f0c88-118">La clase no debe implementar esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f0c88-118">The class should not implement this interface.</span></span>  
  
 <span data-ttu-id="f0c88-119">La clase implementa la interfaz de clase y puede implementar más de una interfaz, pero la primera implementación debe ser la interfaz de clase predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f0c88-119">The class implements the class interface; it can implement more than one interface, but the first implementation will be the default class interface.</span></span> <span data-ttu-id="f0c88-120">Implemente los métodos y propiedades expuestos para COM aquí.</span><span class="sxs-lookup"><span data-stu-id="f0c88-120">Implement the methods and properties exposed to COM here.</span></span> <span data-ttu-id="f0c88-121">Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="f0c88-121">They must be marked public and must match the declarations in the class interface.</span></span> <span data-ttu-id="f0c88-122">Asimismo, declare los eventos iniciados por la clase aquí.</span><span class="sxs-lookup"><span data-stu-id="f0c88-122">Also, declare the events raised by the class here.</span></span> <span data-ttu-id="f0c88-123">Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de eventos.</span><span class="sxs-lookup"><span data-stu-id="f0c88-123">They must be marked public and must match the declarations in the events interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0c88-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0c88-124">Example</span></span>  
 [!code-csharp[csProgGuideInterop#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/ExampleCOM.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="f0c88-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0c88-125">See also</span></span>

- [<span data-ttu-id="f0c88-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f0c88-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f0c88-127">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="f0c88-127">Interoperability</span></span>](./index.md)
- [<span data-ttu-id="f0c88-128">Página Compilar (Diseñador de proyectos) (C#)</span><span class="sxs-lookup"><span data-stu-id="f0c88-128">Build Page, Project Designer (C#)</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)
