---
title: "Cómo: Implementar e invocar un método de extensión personalizado (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a277412c69d26f20721381d9cfa839c7f082f2f2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="09749-102">Cómo: Implementar e invocar un método de extensión personalizado (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="09749-102">How to: Implement and Call a Custom Extension Method (C# Programming Guide)</span></span>
<span data-ttu-id="09749-103">En este tema se muestra cómo implementar sus propios métodos de extensión para cualquier tipo de .NET.</span><span class="sxs-lookup"><span data-stu-id="09749-103">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="09749-104">El código de cliente puede usar los métodos de extensión agregando una referencia a la DLL que los contiene y agregando una directiva [using](../../../csharp/language-reference/keywords/using-directive.md) que especifique el espacio de nombres en el que se definen los métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="09749-104">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../../csharp/language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="09749-105">Para definir y llamar al método de extensión</span><span class="sxs-lookup"><span data-stu-id="09749-105">To define and call the extension method</span></span>  
  
1.  <span data-ttu-id="09749-106">Defina una [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) estática que contenga el método de extensión.</span><span class="sxs-lookup"><span data-stu-id="09749-106">Define a static [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="09749-107">La clase debe estar visible para el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="09749-107">The class must be visible to client code.</span></span> <span data-ttu-id="09749-108">Para obtener más información sobre las reglas de accesibilidad, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="09749-108">For more information about accessibility rules, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
2.  <span data-ttu-id="09749-109">Implemente el método de extensión como un método estático con al menos la misma visibilidad que la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="09749-109">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3.  <span data-ttu-id="09749-110">El primer parámetro del método especifica el tipo en el que opera el método; debe ir precedido del modificador [this](../../../csharp/language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="09749-110">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span>  
  
4.  <span data-ttu-id="09749-111">En el código de llamada, agregue una directiva `using` para especificar el [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md) que contiene la clase del método de extensión.</span><span class="sxs-lookup"><span data-stu-id="09749-111">In the calling code, add a `using` directive to specify the [namespace](../../../csharp/language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5.  <span data-ttu-id="09749-112">Llame a los métodos como si fueran métodos de instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="09749-112">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="09749-113">Tenga en cuenta que el primer parámetro no se especifica mediante el código de llamada, ya que representa el tipo al que se aplica el operador y el compilador ya conoce el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="09749-113">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="09749-114">Solo tiene que proporcionar argumentos para los parámetros comprendidos entre el 2 y `n`.</span><span class="sxs-lookup"><span data-stu-id="09749-114">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09749-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09749-115">Example</span></span>  
 <span data-ttu-id="09749-116">En el ejemplo siguiente se implementa un método de extensión denominado `WordCount` en la clase `CustomExtensions.StringExtension`.</span><span class="sxs-lookup"><span data-stu-id="09749-116">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="09749-117">El método opera en la clase <xref:System.String>, que se especifica como el primer parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="09749-117">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="09749-118">El espacio de nombres `CustomExtensions` se importa en el espacio de nombres de la aplicación y se llama al método dentro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="09749-118">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09749-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="09749-119">Compiling the Code</span></span>  
 <span data-ttu-id="09749-120">Para ejecutar este código, cópielo y péguelo en un proyecto de aplicación de la consola de Visual C# creado en [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09749-120">To run this code, copy and paste it into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="09749-121">De forma predeterminada, este proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y tiene una referencia a System.Core.dll y una directiva `using` para System.Linq.</span><span class="sxs-lookup"><span data-stu-id="09749-121">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="09749-122">Si faltan uno o varios de estos requisitos del proyecto, se pueden agregar manualmente.</span><span class="sxs-lookup"><span data-stu-id="09749-122">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="09749-123">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="09749-123">.NET Framework Security</span></span>  
 <span data-ttu-id="09749-124">Los métodos de extensión no presentan ninguna vulnerabilidad de seguridad específica.</span><span class="sxs-lookup"><span data-stu-id="09749-124">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="09749-125">No se pueden usar nunca para suplantar los métodos existentes en un tipo, porque todos los conflictos de nombres se resuelven a favor de la instancia o del método estático definido por el tipo en cuestión.</span><span class="sxs-lookup"><span data-stu-id="09749-125">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="09749-126">Los métodos de extensión no pueden tener acceso a los datos privados de la clase extendida.</span><span class="sxs-lookup"><span data-stu-id="09749-126">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09749-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="09749-127">See Also</span></span>  
 [<span data-ttu-id="09749-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="09749-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="09749-129">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="09749-129">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [<span data-ttu-id="09749-130">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="09749-130">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="09749-131">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="09749-131">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="09749-132">protected</span><span class="sxs-lookup"><span data-stu-id="09749-132">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="09749-133">internal</span><span class="sxs-lookup"><span data-stu-id="09749-133">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 [<span data-ttu-id="09749-134">public</span><span class="sxs-lookup"><span data-stu-id="09749-134">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="09749-135">this</span><span class="sxs-lookup"><span data-stu-id="09749-135">this</span></span>](../../../csharp/language-reference/keywords/this.md)  
 [<span data-ttu-id="09749-136">namespace</span><span class="sxs-lookup"><span data-stu-id="09749-136">namespace</span></span>](../../../csharp/language-reference/keywords/namespace.md)
