---
title: "Constructores (Guía de programación de C#)"
ms.date: 2017-05-05
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
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
ms.openlocfilehash: 400afcda2fe30bf0e3621ee4c4247486e01d3ee4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="585c6-102">Constructores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="585c6-102">Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="585c6-103">Cada vez que se crea una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md), se llama a su constructor.</span><span class="sxs-lookup"><span data-stu-id="585c6-103">Whenever a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="585c6-104">Una clase o struct puede tener varios constructores que toman argumentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="585c6-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="585c6-105">Los constructores permiten al programador establecer valores predeterminados, limitar la creación de instancias y escribir código flexible y fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="585c6-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="585c6-106">Para obtener más información y ejemplos, vea [Usar constructores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) y [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="585c6-106">For more information and examples, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) and [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="default-constructors"></a><span data-ttu-id="585c6-107">Constructores predeterminados</span><span class="sxs-lookup"><span data-stu-id="585c6-107">Default constructors</span></span>
  
<span data-ttu-id="585c6-108">Si no proporciona un constructor para la clase, C# creará uno de manera predeterminada que cree instancias del objeto y establezca las variables miembro en los valores predeterminados que se indican en [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="585c6-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="585c6-109">Si no proporciona un constructor para su struct, C# se basa en un *constructor predeterminado implícito* para inicializar automáticamente cada campo de un tipo de valor en su valor predeterminado como se muestra en la [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="585c6-109">If you don't provide a constructor for your struct, C# relies on an *implicit default constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="585c6-110">Para obtener más información y ejemplos, vea [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="585c6-110">For more information and examples, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="585c6-111">Sintaxis del constructor</span><span class="sxs-lookup"><span data-stu-id="585c6-111">Constructor syntax</span></span>

<span data-ttu-id="585c6-112">Un constructor es un método cuyo nombre es igual que el nombre de su tipo.</span><span class="sxs-lookup"><span data-stu-id="585c6-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="585c6-113">Su firma del método incluye solo el nombre del método y su lista de parámetros; no incluye un tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="585c6-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="585c6-114">En el ejemplo siguiente se muestra el constructor de una clase denominada `Person`.</span><span class="sxs-lookup"><span data-stu-id="585c6-114">The following example shows the constructor for a class named `Person`.</span></span>

<span data-ttu-id="585c6-115">[!code-cs[constructores](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="585c6-115">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]</span></span>  

<span data-ttu-id="585c6-116">Si un constructor puede implementarse como una instrucción única, puede usar una [definición del cuerpo de expresión](../statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="585c6-116">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="585c6-117">En el ejemplo siguiente se define una clase `Location` cuyo constructor tiene un único parámetro de cadena denominado *name*.</span><span class="sxs-lookup"><span data-stu-id="585c6-117">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="585c6-118">La definición del cuerpo de expresión asigna el argumento al campo `locationName`.</span><span class="sxs-lookup"><span data-stu-id="585c6-118">The expression body definition assigns the argument to the `locationName` field.</span></span>

<span data-ttu-id="585c6-119">[!code-cs[constructor con cuerpo de expresión](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="585c6-119">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span></span>  

## <a name="static-constructors"></a><span data-ttu-id="585c6-120">Constructores estáticos</span><span class="sxs-lookup"><span data-stu-id="585c6-120">Static constructors</span></span>

<span data-ttu-id="585c6-121">En los ejemplos anteriores se han mostrado constructores de instancia, que crean un objeto nuevo.</span><span class="sxs-lookup"><span data-stu-id="585c6-121">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="585c6-122">Una clase o struct también puede tener un constructor estático, que inicializa los miembros estáticos del tipo.</span><span class="sxs-lookup"><span data-stu-id="585c6-122">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="585c6-123">Los constructores estáticos no tienen parámetros.</span><span class="sxs-lookup"><span data-stu-id="585c6-123">Static constructors are parameterless.</span></span> <span data-ttu-id="585c6-124">Si no proporciona un constructor estático para inicializar los campos estáticos, el compilador de C# proporcionará un constructor estático predeterminado que inicializa los campos estáticos en su valor predeterminado como se muestra en la [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="585c6-124">If you don't provide a static constructor to initialize static fields, the C# compiler will supply a default static constructor that initializes static fields to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 

<span data-ttu-id="585c6-125">En el ejemplo siguiente se usa un constructor estático para inicializar un campo estático.</span><span class="sxs-lookup"><span data-stu-id="585c6-125">The following example uses a static constructor to initialize a static field.</span></span>

<span data-ttu-id="585c6-126">[!code-cs[constructores](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="585c6-126">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]</span></span>  

<span data-ttu-id="585c6-127">También puede definir un constructor estático con una definición de cuerpo de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="585c6-127">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

<span data-ttu-id="585c6-128">[!code-cs[constructores](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="585c6-128">[!code-cs[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]</span></span>  

<span data-ttu-id="585c6-129">Para obtener más información y ejemplos, vea [Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="585c6-129">For more information and examples, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="585c6-130">En esta sección</span><span class="sxs-lookup"><span data-stu-id="585c6-130">In This Section</span></span>  
 [<span data-ttu-id="585c6-131">Utilizar constructores</span><span class="sxs-lookup"><span data-stu-id="585c6-131">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [<span data-ttu-id="585c6-132">Constructores de instancias</span><span class="sxs-lookup"><span data-stu-id="585c6-132">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [<span data-ttu-id="585c6-133">Constructores privados</span><span class="sxs-lookup"><span data-stu-id="585c6-133">Private Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [<span data-ttu-id="585c6-134">Constructores estáticos</span><span class="sxs-lookup"><span data-stu-id="585c6-134">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [<span data-ttu-id="585c6-135">Cómo: Escribir un constructor Copy</span><span class="sxs-lookup"><span data-stu-id="585c6-135">How to: Write a Copy Constructor</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="585c6-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="585c6-136">See Also</span></span>  
 <span data-ttu-id="585c6-137">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="585c6-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="585c6-138">[Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="585c6-138">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="585c6-139">[Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="585c6-139">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="585c6-140">[static](../../../csharp/language-reference/keywords/static.md) </span><span class="sxs-lookup"><span data-stu-id="585c6-140">[static](../../../csharp/language-reference/keywords/static.md) </span></span>  
 <span data-ttu-id="585c6-141">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](http://go.microsoft.com/fwlink/?LinkId=112374) (¿Por qué los inicializadores se ejecutan en orden contrario a los constructores? Parte uno)</span><span class="sxs-lookup"><span data-stu-id="585c6-141">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](http://go.microsoft.com/fwlink/?LinkId=112374)</span></span>

