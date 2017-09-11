---
title: "Utilizar estructuras (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 67fa4f764e6e40041e4b8e37eccbd1adb2b509d3
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="6e665-102">Utilizar estructuras (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6e665-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="6e665-103">El tipo `struct` resulta adecuado para representar objetos pequeños como `Point`, `Rectangle`y `Color`.</span><span class="sxs-lookup"><span data-stu-id="6e665-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="6e665-104">Aunque es igual de válido representar un punto como un elemento [class](../../../csharp/language-reference/keywords/class.md) con [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), seguramente un [struct](../../../csharp/language-reference/keywords/struct.md) sea más eficaz en algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="6e665-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="6e665-105">Por ejemplo, si declara una matriz de 1000 objetos `Point` , se asignará más memoria para hacer referencia a cada objeto y, en este caso, un struct sería menos costoso.</span><span class="sxs-lookup"><span data-stu-id="6e665-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="6e665-106">Como [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contiene un objeto denominado <xref:System.Drawing.Point>, denominaremos el struct de este ejemplo "CoOrds".</span><span class="sxs-lookup"><span data-stu-id="6e665-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "CoOrds" instead.</span></span>  
  
 <span data-ttu-id="6e665-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e665-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="6e665-108">Definir un constructor (sin parámetros) predeterminado para un struct es un error,</span><span class="sxs-lookup"><span data-stu-id="6e665-108">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="6e665-109">como también lo es inicializar un campo de instancia en el cuerpo de un struct.</span><span class="sxs-lookup"><span data-stu-id="6e665-109">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="6e665-110">Los miembros del struct solo se pueden inicializar mediante un constructor con parámetros, o bien teniendo acceso individualmente a cada miembro una vez declarado el struct.</span><span class="sxs-lookup"><span data-stu-id="6e665-110">You can initialize struct members only by using a parameterized constructor or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="6e665-111">Los miembros privados o inaccesibles por cualquier otro motivo solo se pueden inicializar en un constructor.</span><span class="sxs-lookup"><span data-stu-id="6e665-111">Any private or otherwise inaccessible members can be initialized only in a constructor.</span></span>  
  
 <span data-ttu-id="6e665-112">Cuando se crea un objeto de struct mediante el operador [new](../../../csharp/language-reference/keywords/new.md) , el objeto se crea y se llama al constructor apropiado.</span><span class="sxs-lookup"><span data-stu-id="6e665-112">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called.</span></span> <span data-ttu-id="6e665-113">A diferencia de las clases, se pueden crear instancias de structs sin usar el operador `new` .</span><span class="sxs-lookup"><span data-stu-id="6e665-113">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="6e665-114">En tal caso, no hay ninguna llamada de constructor, con lo cual la asignación es más eficaz.</span><span class="sxs-lookup"><span data-stu-id="6e665-114">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="6e665-115">Pero los campos seguirán sin asignar y el objeto no se podrá usar hasta que todos los campos se inicialicen.</span><span class="sxs-lookup"><span data-stu-id="6e665-115">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span>  
  
 <span data-ttu-id="6e665-116">Cuando un struct contiene un tipo de referencia como miembro, se debe invocar explícitamente el constructor predeterminado de ese miembro, ya que, de lo contrario, el miembro seguirá sin asignar y el struct no se podrá usar</span><span class="sxs-lookup"><span data-stu-id="6e665-116">When a struct contains a reference type as a member, the default constructor of the member must be invoked explicitly, otherwise the member remains unassigned and the struct cannot be used.</span></span> <span data-ttu-id="6e665-117">(esto genera el error del compilador CS0171).</span><span class="sxs-lookup"><span data-stu-id="6e665-117">(This results in compiler error CS0171.)</span></span>  
  
 <span data-ttu-id="6e665-118">En los structs no existe el concepto de herencia que sí hay en las clases.</span><span class="sxs-lookup"><span data-stu-id="6e665-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="6e665-119">Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase.</span><span class="sxs-lookup"><span data-stu-id="6e665-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="6e665-120">Pero los structs sí heredan de la clase base <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="6e665-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="6e665-121">Un struct puede implementar interfaces y lo hace exactamente igual que las clases.</span><span class="sxs-lookup"><span data-stu-id="6e665-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="6e665-122">No se puede declarar una clase mediante la palabra clave `struct`.</span><span class="sxs-lookup"><span data-stu-id="6e665-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="6e665-123">En C#, las clases y los structs son distintos semánticamente.</span><span class="sxs-lookup"><span data-stu-id="6e665-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="6e665-124">Un struct es un tipo de valor, mientras que una clase es un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="6e665-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="6e665-125">Para obtener más información, vea [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md).</span><span class="sxs-lookup"><span data-stu-id="6e665-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="6e665-126">A menos que necesite una semántica de tipo de referencia, es probable que el sistema controle una clase pequeña más eficazmente si se declara como un struct.</span><span class="sxs-lookup"><span data-stu-id="6e665-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="6e665-127">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="6e665-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="6e665-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e665-128">Description</span></span>  
 <span data-ttu-id="6e665-129">En este ejemplo se muestra la inicialización de `struct` mediante constructores predeterminados y constructores con parámetros.</span><span class="sxs-lookup"><span data-stu-id="6e665-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6e665-130">Código</span><span class="sxs-lookup"><span data-stu-id="6e665-130">Code</span></span>  
 <span data-ttu-id="6e665-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e665-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="6e665-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e665-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="6e665-133">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="6e665-133">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="6e665-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e665-134">Description</span></span>  
 <span data-ttu-id="6e665-135">En este ejemplo se muestra una característica única de los structs.</span><span class="sxs-lookup"><span data-stu-id="6e665-135">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="6e665-136">Se crea un objeto CoOrds sin usar el operador `new` .</span><span class="sxs-lookup"><span data-stu-id="6e665-136">It creates a CoOrds object without using the `new` operator.</span></span> <span data-ttu-id="6e665-137">Si reemplaza la palabra `struct` por la palabra `class`, el programa no se compilará.</span><span class="sxs-lookup"><span data-stu-id="6e665-137">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6e665-138">Código</span><span class="sxs-lookup"><span data-stu-id="6e665-138">Code</span></span>  
 <span data-ttu-id="6e665-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e665-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="6e665-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e665-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e665-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e665-141">See Also</span></span>  
 <span data-ttu-id="6e665-142">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e665-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6e665-143">[Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e665-143">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="6e665-144">Structs</span><span class="sxs-lookup"><span data-stu-id="6e665-144">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

