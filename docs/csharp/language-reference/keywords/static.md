---
title: static (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- static
- static_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8e46dc2f00d1c185379dba1017ca445b9ae5ae72
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="static-c-reference"></a><span data-ttu-id="00f91-102">static (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="00f91-102">static (C# Reference)</span></span>
<span data-ttu-id="00f91-103">Use el modificador `static` para declarar un miembro estático, que pertenece al propio tipo en lugar de a un objeto específico.</span><span class="sxs-lookup"><span data-stu-id="00f91-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="00f91-104">El modificador `static` se puede usar con clases, campos, métodos, propiedades, operadores, eventos y constructores, pero no con indexadores, finalizadores o tipos que no sean clases.</span><span class="sxs-lookup"><span data-stu-id="00f91-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="00f91-105">Para más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="00f91-105">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f91-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00f91-106">Example</span></span>  
 <span data-ttu-id="00f91-107">La siguiente clase se declara como `static` y contiene solo métodos `static`:</span><span class="sxs-lookup"><span data-stu-id="00f91-107">The following class is declared as `static` and contains only `static` methods:</span></span>  
  
 <span data-ttu-id="00f91-108">[!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="00f91-108">[!code-cs[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]</span></span>  
  
 <span data-ttu-id="00f91-109">Una declaración de constantes o tipos es implícitamente un miembro estático.</span><span class="sxs-lookup"><span data-stu-id="00f91-109">A constant or type declaration is implicitly a static member.</span></span>  
  
 <span data-ttu-id="00f91-110">No se puede hacer referencia a los miembros estáticos mediante una instancia.</span><span class="sxs-lookup"><span data-stu-id="00f91-110">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="00f91-111">En su lugar, se hace referencia a ellos a través del nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="00f91-111">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="00f91-112">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="00f91-112">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="00f91-113">[!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="00f91-113">[!code-cs[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]</span></span>  
  
 <span data-ttu-id="00f91-114">Para hacer referencia al miembro estático `x`, use el nombre completo, `MyBaseC.MyStruct.x`, a menos que el miembro sea accesible desde el mismo ámbito:</span><span class="sxs-lookup"><span data-stu-id="00f91-114">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 <span data-ttu-id="00f91-115">Mientras que una instancia de una clase contiene una copia independiente de todos los campos de instancias de la clase, solo existe una copia de cada campo estático.</span><span class="sxs-lookup"><span data-stu-id="00f91-115">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>  
  
 <span data-ttu-id="00f91-116">No se puede usar [this](../../../csharp/language-reference/keywords/this.md) para hacer referencia a métodos estáticos o descriptores de acceso de propiedades.</span><span class="sxs-lookup"><span data-stu-id="00f91-116">It is not possible to use [this](../../../csharp/language-reference/keywords/this.md) to reference static methods or property accessors.</span></span>  
  
 <span data-ttu-id="00f91-117">Si la palabra clave `static` se aplica a una clase, todos los miembros de esta última deben ser estáticos.</span><span class="sxs-lookup"><span data-stu-id="00f91-117">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>  
  
 <span data-ttu-id="00f91-118">Las clases y las clases estáticas pueden tener constructores estáticos.</span><span class="sxs-lookup"><span data-stu-id="00f91-118">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="00f91-119">Se llama a los constructores estáticos en algún momento entre el inicio del programa y la creación de una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="00f91-119">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00f91-120">La palabra clave `static` tiene usos más limitados que en C++.</span><span class="sxs-lookup"><span data-stu-id="00f91-120">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="00f91-121">Para ver una comparación con la palabra clave de C++, vea [Clases de almacenamiento (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="00f91-121">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>
  
 <span data-ttu-id="00f91-122">Para demostrar cómo funcionan los miembros estáticos, imagine una clase que represente el empleado de una empresa.</span><span class="sxs-lookup"><span data-stu-id="00f91-122">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="00f91-123">Supongamos que la clase contiene un método de recuento de empleados y un campo para almacenar el número de empleados.</span><span class="sxs-lookup"><span data-stu-id="00f91-123">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="00f91-124">El método y el campo no pertenecen a ninguna instancia de empleado.</span><span class="sxs-lookup"><span data-stu-id="00f91-124">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="00f91-125">En su lugar, pertenecen a la clase de la empresa.</span><span class="sxs-lookup"><span data-stu-id="00f91-125">Instead they belong to the company class.</span></span> <span data-ttu-id="00f91-126">Por lo tanto, se deben declarar como miembros estáticos de la clase.</span><span class="sxs-lookup"><span data-stu-id="00f91-126">Therefore, they should be declared as static members of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f91-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00f91-127">Example</span></span>  
 <span data-ttu-id="00f91-128">En este ejemplo se lee el nombre y el identificador de un nuevo empleado, se incrementa en uno el recuento de empleados y se muestra la información del nuevo empleado, así como el nuevo número de empleados.</span><span class="sxs-lookup"><span data-stu-id="00f91-128">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="00f91-129">Para que resulte más sencillo, este programa lee el número actual de empleados desde el teclado.</span><span class="sxs-lookup"><span data-stu-id="00f91-129">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="00f91-130">En una aplicación real, esta información se debe leer desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="00f91-130">In a real application, this information should be read from a file.</span></span>  
  
 <span data-ttu-id="00f91-131">[!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="00f91-131">[!code-cs[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f91-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00f91-132">Example</span></span>  
 <span data-ttu-id="00f91-133">En este ejemplo se muestra que, aunque se puede inicializar un campo estático usando otro campo estático que aún no se haya declarado, los resultados serán indefinidos hasta que asigne explícitamente un valor al campo estático.</span><span class="sxs-lookup"><span data-stu-id="00f91-133">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>  
  
 <span data-ttu-id="00f91-134">[!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="00f91-134">[!code-cs[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="00f91-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="00f91-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00f91-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="00f91-136">See Also</span></span>  
 <span data-ttu-id="00f91-137">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="00f91-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="00f91-138">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="00f91-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="00f91-139">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="00f91-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="00f91-140">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md)  (Modificadores [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="00f91-140">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="00f91-141">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="00f91-141">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)

