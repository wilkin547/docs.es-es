---
title: Procedimiento para implementar e invocar un método de extensión personalizado - Guía de programación de C#
description: Aprenda a implementar métodos de extensión para cualquier tipo de .NET. El código de cliente puede usar los métodos mediante la incorporación de una referencia a un archivo DLL y la adición de una directiva using.
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 4ae48a05d451a3276b3a0f2ee4d6c633ce7db306
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513020"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="87b03-104">Procedimiento para implementar e invocar un método de extensión personalizado (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="87b03-104">How to implement and call a custom extension method (C# Programming Guide)</span></span>

<span data-ttu-id="87b03-105">En este tema se muestra cómo implementar sus propios métodos de extensión para cualquier tipo de .NET.</span><span class="sxs-lookup"><span data-stu-id="87b03-105">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="87b03-106">El código de cliente puede usar los métodos de extensión agregando una referencia a la DLL que los contiene y agregando una directiva [using](../../language-reference/keywords/using-directive.md) que especifique el espacio de nombres en el que se definen los métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="87b03-106">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="87b03-107">Para definir y llamar al método de extensión</span><span class="sxs-lookup"><span data-stu-id="87b03-107">To define and call the extension method</span></span>  
  
1. <span data-ttu-id="87b03-108">Defina una [class](./static-classes-and-static-class-members.md) estática que contenga el método de extensión.</span><span class="sxs-lookup"><span data-stu-id="87b03-108">Define a static [class](./static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="87b03-109">La clase debe estar visible para el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="87b03-109">The class must be visible to client code.</span></span> <span data-ttu-id="87b03-110">Para obtener más información sobre las reglas de accesibilidad, vea [Modificadores de acceso](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="87b03-110">For more information about accessibility rules, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
2. <span data-ttu-id="87b03-111">Implemente el método de extensión como un método estático con al menos la misma visibilidad que la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="87b03-111">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3. <span data-ttu-id="87b03-112">El primer parámetro del método especifica el tipo en el que opera el método; debe ir precedido del modificador [this](../../language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="87b03-112">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../language-reference/keywords/this.md) modifier.</span></span>  
  
4. <span data-ttu-id="87b03-113">En el código de llamada, agregue una directiva `using` para especificar el [espacio de nombres](../../language-reference/keywords/namespace.md) que contiene la clase del método de extensión.</span><span class="sxs-lookup"><span data-stu-id="87b03-113">In the calling code, add a `using` directive to specify the [namespace](../../language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5. <span data-ttu-id="87b03-114">Llame a los métodos como si fueran métodos de instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="87b03-114">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="87b03-115">Tenga en cuenta que el primer parámetro no se especifica mediante el código de llamada, ya que representa el tipo al que se aplica el operador y el compilador ya conoce el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="87b03-115">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="87b03-116">Solo tiene que proporcionar argumentos para los parámetros comprendidos entre el 2 y `n`.</span><span class="sxs-lookup"><span data-stu-id="87b03-116">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87b03-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87b03-117">Example</span></span>  

 <span data-ttu-id="87b03-118">En el ejemplo siguiente se implementa un método de extensión denominado `WordCount` en la clase `CustomExtensions.StringExtension`.</span><span class="sxs-lookup"><span data-stu-id="87b03-118">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="87b03-119">El método opera en la clase <xref:System.String>, que se especifica como el primer parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="87b03-119">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="87b03-120">El espacio de nombres `CustomExtensions` se importa en el espacio de nombres de la aplicación y se llama al método dentro del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="87b03-120">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="net-security"></a><span data-ttu-id="87b03-121">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="87b03-121">.NET Security</span></span>  

 <span data-ttu-id="87b03-122">Los métodos de extensión no presentan ninguna vulnerabilidad de seguridad específica.</span><span class="sxs-lookup"><span data-stu-id="87b03-122">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="87b03-123">No se pueden usar nunca para suplantar los métodos existentes en un tipo, porque todos los conflictos de nombres se resuelven a favor de la instancia o del método estático definido por el tipo en cuestión.</span><span class="sxs-lookup"><span data-stu-id="87b03-123">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="87b03-124">Los métodos de extensión no pueden tener acceso a los datos privados de la clase extendida.</span><span class="sxs-lookup"><span data-stu-id="87b03-124">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b03-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="87b03-125">See also</span></span>

- [<span data-ttu-id="87b03-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="87b03-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="87b03-127">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="87b03-127">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="87b03-128">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="87b03-128">LINQ (Language-Integrated Query)</span></span>](../../linq/linq-in-csharp.md)
- [<span data-ttu-id="87b03-129">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="87b03-129">Static Classes and Static Class Members</span></span>](./static-classes-and-static-class-members.md)
- [<span data-ttu-id="87b03-130">protected</span><span class="sxs-lookup"><span data-stu-id="87b03-130">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="87b03-131">internal</span><span class="sxs-lookup"><span data-stu-id="87b03-131">internal</span></span>](../../language-reference/keywords/internal.md)
- [<span data-ttu-id="87b03-132">public</span><span class="sxs-lookup"><span data-stu-id="87b03-132">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="87b03-133">this</span><span class="sxs-lookup"><span data-stu-id="87b03-133">this</span></span>](../../language-reference/keywords/this.md)
- [<span data-ttu-id="87b03-134">namespace</span><span class="sxs-lookup"><span data-stu-id="87b03-134">namespace</span></span>](../../language-reference/keywords/namespace.md)
