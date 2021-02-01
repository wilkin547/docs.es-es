---
title: 'Constructores de instancias: Guía de programación de C#'
description: Los constructores de instancias de C# crean e inicializan variables miembro de instancia cuando se usa la expresión nueva para crear un objeto de una clase.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: 0f9372c744a7bdfab44c8cd020a4378cff729c57
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899040"
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="f8884-103">Constructores de instancias (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f8884-103">Instance Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="f8884-104">Los constructores de instancias se usan para crear e inicializar las variables miembro de instancia cuando se usa la expresión [new](../../language-reference/operators/new-operator.md) para crear un objeto de una [clase](../../language-reference/keywords/class.md).</span><span class="sxs-lookup"><span data-stu-id="f8884-104">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../language-reference/operators/new-operator.md) expression to create an object of a [class](../../language-reference/keywords/class.md).</span></span> <span data-ttu-id="f8884-105">Para inicializar una clase [estática](../../language-reference/keywords/static.md), o variables estáticas en una clase no estática, se define un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="f8884-105">To initialize a [static](../../language-reference/keywords/static.md) class, or static variables in a non-static class, you define a static constructor.</span></span> <span data-ttu-id="f8884-106">Para obtener más información, vea [Constructores estáticos (Guía de programación de C#)](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="f8884-106">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
 <span data-ttu-id="f8884-107">En el siguiente ejemplo se muestra un constructor de instancias:</span><span class="sxs-lookup"><span data-stu-id="f8884-107">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[CoordsWithParameterlessConstructorOnly#1](snippets/instance-constructors/coords/Program.cs#1)]
  
> [!NOTE]
> <span data-ttu-id="f8884-108">Para mayor claridad, esta clase contiene campos públicos.</span><span class="sxs-lookup"><span data-stu-id="f8884-108">For clarity, this class contains public fields.</span></span> <span data-ttu-id="f8884-109">El uso de campos públicos no es una práctica de programación recomendada porque permite que cualquier método de cualquier parte de un programa obtenga acceso sin restricciones ni comprobaciones a los mecanismos internos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="f8884-109">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="f8884-110">Los miembros de datos generalmente deberían ser privados y solo se debería tener acceso a ellos a través de las propiedades y métodos de la clase.</span><span class="sxs-lookup"><span data-stu-id="f8884-110">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="f8884-111">Se llama a este constructor de instancias cada vez que se crea un objeto basado en la clase `Coords`.</span><span class="sxs-lookup"><span data-stu-id="f8884-111">This instance constructor is called whenever an object based on the `Coords` class is created.</span></span> <span data-ttu-id="f8884-112">Un constructor como este, que no toma ningún argumento, se denomina *constructor sin parámetros*.</span><span class="sxs-lookup"><span data-stu-id="f8884-112">A constructor like this one, which takes no arguments, is called a *parameterless constructor*.</span></span> <span data-ttu-id="f8884-113">Pero a menudo resulta útil proporcionar constructores adicionales.</span><span class="sxs-lookup"><span data-stu-id="f8884-113">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="f8884-114">Por ejemplo, se puede agregar un constructor a la clase `Coords` que permita especificar los valores iniciales de los miembros de datos:</span><span class="sxs-lookup"><span data-stu-id="f8884-114">For example, we can add a constructor to the `Coords` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[TwoArgumentConstructor#2](snippets/instance-constructors/coords/Program.cs#2)]
  
 <span data-ttu-id="f8884-115">Esto permite crear objetos `Coords` con valores iniciales predeterminados o específicos, como este:</span><span class="sxs-lookup"><span data-stu-id="f8884-115">This allows `Coords` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[InstantiatingCoords#3](snippets/instance-constructors/coords/Program.cs#3)]
  
 <span data-ttu-id="f8884-116">Si una clase no tiene un constructor, se genera automáticamente un constructor sin parámetros y los valores predeterminados se usan para inicializar los campos del objeto.</span><span class="sxs-lookup"><span data-stu-id="f8884-116">If a class does not have a constructor, a parameterless constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="f8884-117">Por ejemplo, un [int](../../language-reference/builtin-types/integral-numeric-types.md) se inicializa en 0.</span><span class="sxs-lookup"><span data-stu-id="f8884-117">For example, an [int](../../language-reference/builtin-types/integral-numeric-types.md) is initialized to 0.</span></span> <span data-ttu-id="f8884-118">Para obtener información sobre los valores predeterminados de los tipos, vea [Valores predeterminados de los tipos de C#](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="f8884-118">For information about the type default values, see [Default values of C# types](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="f8884-119">Por tanto, dado que el constructor sin parámetros de la clase `Coords` inicializa todos los miembros de datos en cero, se puede quitar por completo sin cambiar el funcionamiento de la clase.</span><span class="sxs-lookup"><span data-stu-id="f8884-119">Therefore, because the `Coords` class parameterless constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="f8884-120">Más adelante en este tema se proporciona un ejemplo completo del uso de varios constructores en el Ejemplo 1 y en el Ejemplo 2 se proporciona un ejemplo de un constructor generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f8884-120">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="f8884-121">Los constructores de instancias también se pueden usar para llamar a los constructores de instancias de las clases base.</span><span class="sxs-lookup"><span data-stu-id="f8884-121">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="f8884-122">El constructor de clase puede invocar el constructor de la clase base a través del inicializador, como sigue:</span><span class="sxs-lookup"><span data-stu-id="f8884-122">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
```csharp
class Circle : Shape
{
    public Circle(double radius)
        : base(radius, 0)
    {
    }
}
```
  
 <span data-ttu-id="f8884-123">En este ejemplo, la clase `Circle` pasa valores que representan el radio y el alto al constructor proporcionado por `Shape` desde el que se deriva `Circle`.</span><span class="sxs-lookup"><span data-stu-id="f8884-123">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="f8884-124">Un ejemplo completo del uso de `Shape` y `Circle` aparece en este tema en el Ejemplo 3.</span><span class="sxs-lookup"><span data-stu-id="f8884-124">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="f8884-125">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f8884-125">Example 1</span></span>  

 <span data-ttu-id="f8884-126">En el ejemplo siguiente se muestra una clase con dos constructores de clase, uno sin argumentos y uno con dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="f8884-126">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[CoordsFullExample#4](snippets/instance-constructors/coords/Program.cs#4)]
  
## <a name="example-2"></a><span data-ttu-id="f8884-127">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="f8884-127">Example 2</span></span>  

 <span data-ttu-id="f8884-128">En este ejemplo, la clase `Person` no tiene ningún constructor, en cuyo caso, se proporciona automáticamente un constructor sin parámetros y los campos se inicializan en sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="f8884-128">In this example, the class `Person` does not have any constructors, in which case, a parameterless constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[Person](snippets/instance-constructors/person/Program.cs)]
  
 <span data-ttu-id="f8884-129">Observe que el valor predeterminado de `age` es `0` y el valor predeterminado de `name` es `null`.</span><span class="sxs-lookup"><span data-stu-id="f8884-129">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="f8884-130">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="f8884-130">Example 3</span></span>  

 <span data-ttu-id="f8884-131">En el ejemplo siguiente se muestra cómo usar el inicializador de la clase base.</span><span class="sxs-lookup"><span data-stu-id="f8884-131">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="f8884-132">La clase `Circle` se deriva de la clase general `Shape` y la clase `Cylinder` se deriva de la clase `Circle`.</span><span class="sxs-lookup"><span data-stu-id="f8884-132">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="f8884-133">En cada clase derivada, el constructor usa su inicializador de clase base.</span><span class="sxs-lookup"><span data-stu-id="f8884-133">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[ShapesExample](snippets/instance-constructors/shapes/Program.cs)]
  
 <span data-ttu-id="f8884-134">Para obtener más ejemplos sobre cómo invocar los constructores de clase base, vea [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) y [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="f8884-134">For more examples on invoking the base class constructors, see [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md), and [base](../../language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8884-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8884-135">See also</span></span>

- [<span data-ttu-id="f8884-136">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f8884-136">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f8884-137">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="f8884-137">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="f8884-138">Constructores</span><span class="sxs-lookup"><span data-stu-id="f8884-138">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="f8884-139">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="f8884-139">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="f8884-140">static</span><span class="sxs-lookup"><span data-stu-id="f8884-140">static</span></span>](../../language-reference/keywords/static.md)
