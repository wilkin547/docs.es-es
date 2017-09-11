---
title: "Constructores de instancias (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
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
ms.openlocfilehash: f93f622d5bf99ab7e8b1d8338192ff58472813dd
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="90418-102">Constructores de instancias (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="90418-102">Instance Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="90418-103">Los constructores de instancias se usan para crear e inicializar las variables miembro de instancia cuando se usa la expresión [new](../../../csharp/language-reference/keywords/new.md) para crear un objeto de una [clase](../../../csharp/language-reference/keywords/class.md).</span><span class="sxs-lookup"><span data-stu-id="90418-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../../csharp/language-reference/keywords/new.md) expression to create an object of a [class](../../../csharp/language-reference/keywords/class.md).</span></span> <span data-ttu-id="90418-104">Para inicializar una clase [estática](../../../csharp/language-reference/keywords/static.md), o variables estáticas en una clase no estática, se debe definir un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="90418-104">To initialize a [static](../../../csharp/language-reference/keywords/static.md) class, or static variables in a non-static class, you must define a static constructor.</span></span> <span data-ttu-id="90418-105">Para obtener más información, vea [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md) (Constructores estáticos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="90418-105">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
 <span data-ttu-id="90418-106">En el siguiente ejemplo se muestra un constructor de instancias:</span><span class="sxs-lookup"><span data-stu-id="90418-106">The following example shows an instance constructor:</span></span>  
  
 <span data-ttu-id="90418-107">[!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="90418-107">[!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90418-108">Para mayor claridad, esta clase contiene campos públicos.</span><span class="sxs-lookup"><span data-stu-id="90418-108">For clarity, this class contains public fields.</span></span> <span data-ttu-id="90418-109">El uso de campos públicos no es una práctica de programación recomendada porque permite que cualquier método de cualquier parte de un programa obtenga acceso sin restricciones ni comprobaciones a los mecanismos internos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="90418-109">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="90418-110">Los miembros de datos generalmente deberían ser privados y solo se debería tener acceso a ellos a través de las propiedades y métodos de la clase.</span><span class="sxs-lookup"><span data-stu-id="90418-110">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="90418-111">Se llama a este constructor de instancias cada vez que se crea un objeto basado en la clase `CoOrds`.</span><span class="sxs-lookup"><span data-stu-id="90418-111">This instance constructor is called whenever an object based on the `CoOrds` class is created.</span></span> <span data-ttu-id="90418-112">Un constructor como este, que no toma ningún argumento, se denomina *constructor predeterminado*.</span><span class="sxs-lookup"><span data-stu-id="90418-112">A constructor like this one, which takes no arguments, is called a *default constructor*.</span></span> <span data-ttu-id="90418-113">Pero a menudo resulta útil proporcionar constructores adicionales.</span><span class="sxs-lookup"><span data-stu-id="90418-113">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="90418-114">Por ejemplo, se puede agregar un constructor a la clase `CoOrds` que permita especificar los valores iniciales de los miembros de datos:</span><span class="sxs-lookup"><span data-stu-id="90418-114">For example, we can add a constructor to the `CoOrds` class that allows us to specify the initial values for the data members:</span></span>  
  
 <span data-ttu-id="90418-115">[!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="90418-115">[!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="90418-116">Esto permite crear objetos `CoOrd` con valores iniciales predeterminados o específicos, como este:</span><span class="sxs-lookup"><span data-stu-id="90418-116">This allows `CoOrd` objects to be created with default or specific initial values, like this:</span></span>  
  
 <span data-ttu-id="90418-117">[!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="90418-117">[!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]</span></span>  
  
 <span data-ttu-id="90418-118">Si una clase no tiene un constructor, se genera automáticamente un constructor predeterminado y los valores predeterminados se usan para inicializar los campos del objeto.</span><span class="sxs-lookup"><span data-stu-id="90418-118">If a class does not have a constructor, a default constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="90418-119">Por ejemplo, un [int](../../../csharp/language-reference/keywords/int.md) se inicializa en 0.</span><span class="sxs-lookup"><span data-stu-id="90418-119">For example, an [int](../../../csharp/language-reference/keywords/int.md) is initialized to 0.</span></span> <span data-ttu-id="90418-120">Para más información sobre los valores predeterminados, vea [Tabla de valores predeterminados (Referencia de C#)](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="90418-120">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="90418-121">Por tanto, dado que el constructor predeterminado de la clase `CoOrds` inicializa todos los miembros de datos en cero, se puede quitar por completo sin cambiar el funcionamiento de la clase.</span><span class="sxs-lookup"><span data-stu-id="90418-121">Therefore, because the `CoOrds` class default constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="90418-122">Más adelante en este tema se proporciona un ejemplo completo del uso de varios constructores en el Ejemplo 1 y en el Ejemplo 2 se proporciona un ejemplo de un constructor generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="90418-122">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="90418-123">Los constructores de instancias también se pueden usar para llamar a los constructores de instancias de las clases base.</span><span class="sxs-lookup"><span data-stu-id="90418-123">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="90418-124">El constructor de clase puede invocar el constructor de la clase base a través del inicializador, como sigue:</span><span class="sxs-lookup"><span data-stu-id="90418-124">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 <span data-ttu-id="90418-125">[!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="90418-125">[!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]</span></span>  
  
 <span data-ttu-id="90418-126">En este ejemplo, la clase `Circle` pasa valores que representan el radio y el alto al constructor proporcionado por `Shape` desde el que se deriva `Circle`.</span><span class="sxs-lookup"><span data-stu-id="90418-126">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="90418-127">Un ejemplo completo del uso de `Shape` y `Circle` aparece en este tema en el Ejemplo 3.</span><span class="sxs-lookup"><span data-stu-id="90418-127">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="90418-128">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="90418-128">Example 1</span></span>  
 <span data-ttu-id="90418-129">En el ejemplo siguiente se muestra una clase con dos constructores de clase, uno sin argumentos y uno con dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="90418-129">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 <span data-ttu-id="90418-130">[!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="90418-130">[!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="90418-131">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="90418-131">Example 2</span></span>  
 <span data-ttu-id="90418-132">En este ejemplo, la clase `Person` no tiene ningún constructor, en cuyo caso, se proporciona automáticamente un constructor predeterminado y los campos se inicializan en sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="90418-132">In this example, the class `Person` does not have any constructors, in which case, a default constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 <span data-ttu-id="90418-133">[!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="90418-133">[!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]</span></span>  
  
 <span data-ttu-id="90418-134">Observe que el valor predeterminado de `age` es `0` y el valor predeterminado de `name` es `null`.</span><span class="sxs-lookup"><span data-stu-id="90418-134">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span> <span data-ttu-id="90418-135">Para más información sobre los valores predeterminados, vea [Tabla de valores predeterminados (Referencia de C#)](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="90418-135">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="90418-136">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="90418-136">Example 3</span></span>  
 <span data-ttu-id="90418-137">En el ejemplo siguiente se muestra cómo usar el inicializador de la clase base.</span><span class="sxs-lookup"><span data-stu-id="90418-137">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="90418-138">La clase `Circle` se deriva de la clase general `Shape` y la clase `Cylinder` se deriva de la clase `Circle`.</span><span class="sxs-lookup"><span data-stu-id="90418-138">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="90418-139">En cada clase derivada, el constructor usa su inicializador de clase base.</span><span class="sxs-lookup"><span data-stu-id="90418-139">The constructor on each derived class is using its base class initializer.</span></span>  
  
 <span data-ttu-id="90418-140">[!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="90418-140">[!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]</span></span>  
  
 <span data-ttu-id="90418-141">Para obtener más ejemplos sobre cómo invocar los constructores de clase base, vea [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md) y [base](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="90418-141">For more examples on invoking the base class constructors, see [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), and [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90418-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="90418-142">See Also</span></span>  
 <span data-ttu-id="90418-143">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="90418-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="90418-144">[Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="90418-144">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="90418-145">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md)  (Constructores [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="90418-145">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="90418-146">[Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="90418-146">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 [<span data-ttu-id="90418-147">static</span><span class="sxs-lookup"><span data-stu-id="90418-147">static</span></span>](../../../csharp/language-reference/keywords/static.md)

