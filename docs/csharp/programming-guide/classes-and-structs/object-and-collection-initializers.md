---
title: "Inicializadores de objeto y de colección (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 628f08aaebfa209fc9cb7cfb2b506fc67d5424f9
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2018
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="97108-102">Inicializadores de objeto y de colección (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="97108-102">Object and Collection Initializers (C# Programming Guide)</span></span>
<span data-ttu-id="97108-103">Los inicializadores de objeto permiten asignar valores a cualquier campo o propiedad accesible de un objeto en el momento de su creación sin tener que invocar un constructor seguido de líneas de instrucciones de asignación.</span><span class="sxs-lookup"><span data-stu-id="97108-103">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="97108-104">La sintaxis de inicializador de objetos permite especificar argumentos para un constructor u omitir los argumentos (y la sintaxis de paréntesis).</span><span class="sxs-lookup"><span data-stu-id="97108-104">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="97108-105">En el ejemplo siguiente se muestra cómo usar un inicializador de objeto con un tipo con nombre, `Cat`, y cómo invocar el constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="97108-105">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the default constructor.</span></span> <span data-ttu-id="97108-106">Tenga en cuenta el uso de propiedades implementadas automáticamente en la clase `Cat`.</span><span class="sxs-lookup"><span data-stu-id="97108-106">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="97108-107">Para obtener más información, vea [Propiedades implementadas automáticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="97108-107">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
<span data-ttu-id="97108-108">La sintaxis de los inicializadores de objeto le permite crear una instancia, y después asigna el objeto recién creado, con las propiedades asignadas, a la variable de la asignación.</span><span class="sxs-lookup"><span data-stu-id="97108-108">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>
  
## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="97108-109">Inicializadores de objeto con tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="97108-109">Object Initializers with anonymous types</span></span>  
 <span data-ttu-id="97108-110">Aunque los inicializadores de objeto se pueden usar en cualquier contexto, resultan especialmente útiles en las expresiones de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97108-110">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="97108-111">Las expresiones de consulta usan con frecuencia [tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), que solo se pueden inicializar con un inicializador de objeto, como se muestra en la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="97108-111">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 <span data-ttu-id="97108-112">Los tipos anónimos permiten a la cláusula `select` de una expresión de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] transformar objetos de la secuencia original en objetos cuyo valor y forma pueden ser distintos de los originales.</span><span class="sxs-lookup"><span data-stu-id="97108-112">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="97108-113">Esto resulta útil si desea almacenar solo una parte de la información de cada objeto en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="97108-113">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="97108-114">En el ejemplo siguiente, suponga que un objeto del producto (`p`) contiene numerosos campos y métodos y que solo le interesa crear una secuencia de objetos que contenga el nombre del producto y el precio por unidad.</span><span class="sxs-lookup"><span data-stu-id="97108-114">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 <span data-ttu-id="97108-115">Al ejecutarse esta consulta, la variable `productInfos` incluirá una secuencia de objetos a la que se puede tener acceso en una instrucción `foreach`, como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="97108-115">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 <span data-ttu-id="97108-116">Cada uno de los objetos del nuevo tipo anónimo tiene dos propiedades públicas que reciben los mismos nombres que las propiedades o campos del objeto original.</span><span class="sxs-lookup"><span data-stu-id="97108-116">Each object in the new anonymous type has two public properties which receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="97108-117">También puede cambiar el nombre de un campo al crear un tipo anónimo; en el ejemplo siguiente se cambia el nombre del campo `UnitPrice` a `Price`.</span><span class="sxs-lookup"><span data-stu-id="97108-117">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a><span data-ttu-id="97108-118">Inicializadores de objeto con tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="97108-118">Object initializers with nullable types</span></span>  
 <span data-ttu-id="97108-119">Es un error en tiempo de compilación usar un inicializador de objeto con un struct que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="97108-119">It is a compile-time error to use an object initializer with a nullable struct.</span></span>  
  
## <a name="collection-initializers"></a><span data-ttu-id="97108-120">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="97108-120">Collection initializers</span></span>  
 <span data-ttu-id="97108-121">Los inicializadores de colección le permiten especificar uno o varios inicializadores de elemento al inicializar un tipo de colección que implementa <xref:System.Collections.IEnumerable> y tiene `Add` con la firma apropiada como un método de instancia o un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="97108-121">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="97108-122">Los inicializadores de elemento pueden ser un valor simple, una expresión o un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="97108-122">The element initializers can be a simple value, an expression or an object initializer.</span></span> <span data-ttu-id="97108-123">Si se usa un inicializador de colección, no es necesario especificar varias llamadas al método `Add` de la clase en el código fuente; el compilador agrega las llamadas.</span><span class="sxs-lookup"><span data-stu-id="97108-123">By using a collection initializer you do not have to specify multiple calls to the `Add` method of the class in your source code; the compiler adds the calls.</span></span>  
  
 <span data-ttu-id="97108-124">En los ejemplos siguientes se muestran dos inicializadores de colección simples:</span><span class="sxs-lookup"><span data-stu-id="97108-124">The following examples shows two simple collection initializers:</span></span>  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 <span data-ttu-id="97108-125">El inicializador de colección siguiente usa inicializadores de objeto para inicializar los objetos de la clase `Cat` definida en un ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="97108-125">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="97108-126">Observe que los inicializadores de objeto individuales se escriben entre llaves y se separan por comas.</span><span class="sxs-lookup"><span data-stu-id="97108-126">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 <span data-ttu-id="97108-127">Puede especificar [null](../../../csharp/language-reference/keywords/null.md) como elemento de un inicializador de colección si el método `Add` de la colección lo permite.</span><span class="sxs-lookup"><span data-stu-id="97108-127">You can specify [null](../../../csharp/language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 <span data-ttu-id="97108-128">Puede especificar elementos indexados si la colección admite la indexación.</span><span class="sxs-lookup"><span data-stu-id="97108-128">You can specify indexed elements if the collection supports indexing.</span></span>  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="examples"></a><span data-ttu-id="97108-129">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="97108-129">Examples</span></span>

 <span data-ttu-id="97108-130">En el ejemplo siguiente se combinan los conceptos de inicializadores de objeto y colección.</span><span class="sxs-lookup"><span data-stu-id="97108-130">The following example combines the concepts of object and collection initializers.</span></span>

 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
 
 <span data-ttu-id="97108-131">Como se muestra en el ejemplo siguiente, un objeto que implementa <xref:System.Collections.IEnumerable> y que contiene un método `Add` con varios parámetros permite inicializadores de colección con varios elementos por cada elemento de la lista correspondiente a la firma del método `Add`.</span><span class="sxs-lookup"><span data-stu-id="97108-131">Shown in the following example, an object which implements <xref:System.Collections.IEnumerable> containing an `Add` method with multiple parameters allows for collection initializers with multiple elements per item in the list corresponding to the signature of the `Add` method.</span></span> 
 
 [!code-csharp[csProgGuideLINQ#84](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_7.cs)]
 
 <span data-ttu-id="97108-132">Los métodos `Add` pueden usar la palabra clave `params` para tomar un número variable de argumentos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="97108-132">`Add` methods can use the `params` keyword to take a variable number of arguments as shown in the following example.</span></span> <span data-ttu-id="97108-133">En este ejemplo se muestra la implementación personalizada de un indexador también para inicializar una colección mediante índices.</span><span class="sxs-lookup"><span data-stu-id="97108-133">This example demonstrates the custom implementation of an indexer as well to initialize a collection using indexes.</span></span>
 
 [!code-csharp[csProgGuideLINQ#85](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_8.cs)]
 
## <a name="see-also"></a><span data-ttu-id="97108-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="97108-134">See Also</span></span>  
 [<span data-ttu-id="97108-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="97108-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="97108-136">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="97108-136">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="97108-137">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="97108-137">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
