---
title: 'Constructores: Guía de programación de C#'
ms.custom: seodec18
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 79b000952ed03e5dc28d1c33bd2cba14708fb26a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235337"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="0a95d-102">Constructores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0a95d-102">Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="0a95d-103">Cada vez que se crea una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md), se llama a su constructor.</span><span class="sxs-lookup"><span data-stu-id="0a95d-103">Whenever a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="0a95d-104">Una clase o struct puede tener varios constructores que toman argumentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="0a95d-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="0a95d-105">Los constructores permiten al programador establecer valores predeterminados, limitar la creación de instancias y escribir código flexible y fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="0a95d-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="0a95d-106">Para obtener más información y ejemplos, vea [Usar constructores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) y [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0a95d-106">For more information and examples, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) and [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="default-constructors"></a><span data-ttu-id="0a95d-107">Constructores predeterminados</span><span class="sxs-lookup"><span data-stu-id="0a95d-107">Default constructors</span></span>
  
<span data-ttu-id="0a95d-108">Si no proporciona un constructor para la clase, C# creará uno de manera predeterminada que cree instancias del objeto y establezca las variables miembro en los valores predeterminados que se indican en [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0a95d-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="0a95d-109">Si no proporciona un constructor para su struct, C# se basa en un *constructor predeterminado implícito* para inicializar automáticamente cada campo de un tipo de valor en su valor predeterminado como se muestra en la [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0a95d-109">If you don't provide a constructor for your struct, C# relies on an *implicit default constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="0a95d-110">Para obtener más información y ejemplos, vea [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0a95d-110">For more information and examples, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="0a95d-111">Sintaxis del constructor</span><span class="sxs-lookup"><span data-stu-id="0a95d-111">Constructor syntax</span></span>

<span data-ttu-id="0a95d-112">Un constructor es un método cuyo nombre es igual que el nombre de su tipo.</span><span class="sxs-lookup"><span data-stu-id="0a95d-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="0a95d-113">Su firma del método incluye solo el nombre del método y su lista de parámetros; no incluye un tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0a95d-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="0a95d-114">En el ejemplo siguiente se muestra el constructor de una clase denominada `Person`.</span><span class="sxs-lookup"><span data-stu-id="0a95d-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="0a95d-115">Si un constructor puede implementarse como una instrucción única, puede usar una [definición del cuerpo de expresión](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="0a95d-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="0a95d-116">En el ejemplo siguiente se define una clase `Location` cuyo constructor tiene un único parámetro de cadena denominado *name*.</span><span class="sxs-lookup"><span data-stu-id="0a95d-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="0a95d-117">La definición del cuerpo de expresión asigna el argumento al campo `locationName`.</span><span class="sxs-lookup"><span data-stu-id="0a95d-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="0a95d-118">Constructores estáticos</span><span class="sxs-lookup"><span data-stu-id="0a95d-118">Static constructors</span></span>

<span data-ttu-id="0a95d-119">En los ejemplos anteriores se han mostrado constructores de instancia, que crean un objeto nuevo.</span><span class="sxs-lookup"><span data-stu-id="0a95d-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="0a95d-120">Una clase o struct también puede tener un constructor estático, que inicializa los miembros estáticos del tipo.</span><span class="sxs-lookup"><span data-stu-id="0a95d-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="0a95d-121">Los constructores estáticos no tienen parámetros.</span><span class="sxs-lookup"><span data-stu-id="0a95d-121">Static constructors are parameterless.</span></span> <span data-ttu-id="0a95d-122">Si no proporciona un constructor estático para inicializar los campos estáticos, el compilador de C# proporcionará un constructor estático predeterminado que inicializa los campos estáticos en su valor predeterminado como se muestra en la [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="0a95d-122">If you don't provide a static constructor to initialize static fields, the C# compiler will supply a default static constructor that initializes static fields to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 

<span data-ttu-id="0a95d-123">En el ejemplo siguiente se usa un constructor estático para inicializar un campo estático.</span><span class="sxs-lookup"><span data-stu-id="0a95d-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="0a95d-124">También puede definir un constructor estático con una definición de cuerpo de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0a95d-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="0a95d-125">Para obtener más información y ejemplos, vea [Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0a95d-125">For more information and examples, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a95d-126">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0a95d-126">In This Section</span></span>  
 [<span data-ttu-id="0a95d-127">Utilizar constructores</span><span class="sxs-lookup"><span data-stu-id="0a95d-127">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [<span data-ttu-id="0a95d-128">Constructores de instancias</span><span class="sxs-lookup"><span data-stu-id="0a95d-128">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [<span data-ttu-id="0a95d-129">Constructores privados</span><span class="sxs-lookup"><span data-stu-id="0a95d-129">Private Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [<span data-ttu-id="0a95d-130">Constructores estáticos</span><span class="sxs-lookup"><span data-stu-id="0a95d-130">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [<span data-ttu-id="0a95d-131">Cómo: Escribir un constructor Copy</span><span class="sxs-lookup"><span data-stu-id="0a95d-131">How to: Write a Copy Constructor</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a95d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a95d-132">See Also</span></span>

- [<span data-ttu-id="0a95d-133">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0a95d-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0a95d-134">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="0a95d-134">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="0a95d-135">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="0a95d-135">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [<span data-ttu-id="0a95d-136">static</span><span class="sxs-lookup"><span data-stu-id="0a95d-136">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
- <span data-ttu-id="0a95d-137">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one) (¿Por qué los inicializadores se ejecutan en orden contrario a los constructores? Parte uno)</span><span class="sxs-lookup"><span data-stu-id="0a95d-137">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)</span></span>
