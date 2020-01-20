---
title: 'Inicializadores de objeto y de colección: Guía de programación de C#'
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 5565f37c9cfd8cb84c07f9ecc6f6c2edf8c66c61
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714751"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="c75f5-102">Inicializadores de objeto y de colección (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c75f5-102">Object and Collection Initializers (C# Programming Guide)</span></span>

<span data-ttu-id="c75f5-103">C# permite crear instancias de un objeto o colección y realizar asignaciones de miembros en una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="c75f5-103">C# lets you instantiate an object or collection and perform member assignments in a single statement.</span></span>

## <a name="object-initializers"></a><span data-ttu-id="c75f5-104">Inicializadores de objeto</span><span class="sxs-lookup"><span data-stu-id="c75f5-104">Object initializers</span></span>

<span data-ttu-id="c75f5-105">Los inicializadores de objeto permiten asignar valores a cualquier campo o propiedad accesible de un objeto en el momento de su creación sin tener que invocar un constructor seguido de líneas de instrucciones de asignación.</span><span class="sxs-lookup"><span data-stu-id="c75f5-105">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="c75f5-106">La sintaxis de inicializador de objetos permite especificar argumentos para un constructor u omitir los argumentos (y la sintaxis de paréntesis).</span><span class="sxs-lookup"><span data-stu-id="c75f5-106">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="c75f5-107">En el ejemplo siguiente se muestra cómo usar un inicializador de objeto con un tipo con nombre, `Cat`, y cómo invocar el constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="c75f5-107">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the parameterless constructor.</span></span> <span data-ttu-id="c75f5-108">Tenga en cuenta el uso de propiedades implementadas automáticamente en la clase `Cat`.</span><span class="sxs-lookup"><span data-stu-id="c75f5-108">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="c75f5-109">Para obtener más información, vea [Propiedades implementadas automáticamente](auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c75f5-109">For more information, see [Auto-Implemented Properties](auto-implemented-properties.md).</span></span>  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  
 
<span data-ttu-id="c75f5-110">La sintaxis de los inicializadores de objeto le permite crear una instancia, y después asigna el objeto recién creado, con las propiedades asignadas, a la variable de la asignación.</span><span class="sxs-lookup"><span data-stu-id="c75f5-110">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>

<span data-ttu-id="c75f5-111">A partir de C# 6, los inicializadores de objeto pueden establecer indizadores, además de asignar campos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="c75f5-111">Starting with C# 6, object initializers can set indexers, in addition to assigning fields and properties.</span></span> <span data-ttu-id="c75f5-112">Tenga en cuenta esta clase básica `Matrix`:</span><span class="sxs-lookup"><span data-stu-id="c75f5-112">Consider this basic `Matrix` class:</span></span>

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

<span data-ttu-id="c75f5-113">Se podría inicializar la matriz de identidad con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c75f5-113">You could initialize the identity matrix with the following code:</span></span>

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

<span data-ttu-id="c75f5-114">Puede usarse cualquier indizador accesible que contenga un establecedor accesible como una de las expresiones de un inicializador de objeto, independientemente del número o los tipos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="c75f5-114">Any accessible indexer that contains an accessible setter can be used as one of the expressions in an object initializer, regardless of the number or types of arguments.</span></span> <span data-ttu-id="c75f5-115">Los argumentos del índice forman el lado izquierdo de la asignación, mientras que el valor es el lado derecho de la expresión.</span><span class="sxs-lookup"><span data-stu-id="c75f5-115">The index arguments form the left side of the assignment, and the value is the right side of the expression.</span></span>  <span data-ttu-id="c75f5-116">Por ejemplo, todos estos son válidos si `IndexersExample` tiene los indizadores adecuados:</span><span class="sxs-lookup"><span data-stu-id="c75f5-116">For example, these are all valid if `IndexersExample` has the appropriate indexers:</span></span>

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

<span data-ttu-id="c75f5-117">Para que el código anterior se compile, el tipo `IndexersExample` debe tener los siguientes miembros:</span><span class="sxs-lookup"><span data-stu-id="c75f5-117">For the preceding code to compile, the `IndexersExample` type must have the following members:</span></span>

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="c75f5-118">Inicializadores de objeto con tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="c75f5-118">Object Initializers with anonymous types</span></span>

<span data-ttu-id="c75f5-119">Aunque los inicializadores de objeto se pueden usar en cualquier contexto, resultan especialmente útiles en las expresiones de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="c75f5-119">Although object initializers can be used in any context, they are especially useful in LINQ query expressions.</span></span> <span data-ttu-id="c75f5-120">Las expresiones de consulta usan con frecuencia [tipos anónimos](./anonymous-types.md), que solo se pueden inicializar con un inicializador de objeto, como se muestra en la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="c75f5-120">Query expressions make frequent use of [anonymous types](./anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

<span data-ttu-id="c75f5-121">Los tipos anónimos permiten a la cláusula `select` de una expresión de consulta LINQ transformar objetos de la secuencia original en objetos cuyo valor y forma pueden ser distintos de los originales.</span><span class="sxs-lookup"><span data-stu-id="c75f5-121">Anonymous types enable the `select` clause in a LINQ query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="c75f5-122">Esto resulta útil si desea almacenar solo una parte de la información de cada objeto en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="c75f5-122">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="c75f5-123">En el ejemplo siguiente, suponga que un objeto del producto (`p`) contiene numerosos campos y métodos y que solo le interesa crear una secuencia de objetos que contenga el nombre del producto y el precio por unidad.</span><span class="sxs-lookup"><span data-stu-id="c75f5-123">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

<span data-ttu-id="c75f5-124">Al ejecutarse esta consulta, la variable `productInfos` incluirá una secuencia de objetos a la que se puede tener acceso en una instrucción `foreach`, como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c75f5-124">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  

```csharp
foreach(var p in productInfos){...}  
```

<span data-ttu-id="c75f5-125">Cada objeto del nuevo tipo anónimo tiene dos propiedades públicas que reciben los mismos nombres que las propiedades o los campos del objeto original.</span><span class="sxs-lookup"><span data-stu-id="c75f5-125">Each object in the new anonymous type has two public properties that receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="c75f5-126">También puede cambiar el nombre de un campo al crear un tipo anónimo; en el ejemplo siguiente se cambia el nombre del campo `UnitPrice` a `Price`.</span><span class="sxs-lookup"><span data-stu-id="c75f5-126">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a><span data-ttu-id="c75f5-127">Inicializadores de colección</span><span class="sxs-lookup"><span data-stu-id="c75f5-127">Collection initializers</span></span>

<span data-ttu-id="c75f5-128">Los inicializadores de colección le permiten especificar uno o varios inicializadores de elemento al inicializar un tipo de colección que implementa <xref:System.Collections.IEnumerable> y tiene `Add` con la firma apropiada como un método de instancia o un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="c75f5-128">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="c75f5-129">Los inicializadores de elemento pueden ser un valor simple, una expresión o un inicializador de objeto.</span><span class="sxs-lookup"><span data-stu-id="c75f5-129">The element initializers can be a simple value, an expression, or an object initializer.</span></span> <span data-ttu-id="c75f5-130">Si se usa un inicializador de colección, no es necesario especificar varias llamadas; el compilador las agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c75f5-130">By using a collection initializer, you do not have to specify multiple calls; the compiler adds the calls automatically.</span></span>  
  
<span data-ttu-id="c75f5-131">En el ejemplo siguiente se muestran dos inicializadores de colección simples:</span><span class="sxs-lookup"><span data-stu-id="c75f5-131">The following example shows two simple collection initializers:</span></span>  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

<span data-ttu-id="c75f5-132">El inicializador de colección siguiente usa inicializadores de objeto para inicializar los objetos de la clase `Cat` definida en un ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c75f5-132">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="c75f5-133">Observe que los inicializadores de objeto individuales se escriben entre llaves y se separan por comas.</span><span class="sxs-lookup"><span data-stu-id="c75f5-133">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
<span data-ttu-id="c75f5-134">Puede especificar [null](../../language-reference/keywords/null.md) como elemento de un inicializador de colección si el método `Add` de la colección lo permite.</span><span class="sxs-lookup"><span data-stu-id="c75f5-134">You can specify [null](../../language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 <span data-ttu-id="c75f5-135">Puede especificar elementos indexados si la colección admite indexación de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="c75f5-135">You can specify indexed elements if the collection supports read / write indexing.</span></span>
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

<span data-ttu-id="c75f5-136">El ejemplo anterior genera código que llama a <xref:System.Collections.Generic.Dictionary%602.Item(%600)> para establecer los valores.</span><span class="sxs-lookup"><span data-stu-id="c75f5-136">The preceding sample generates code that calls the <xref:System.Collections.Generic.Dictionary%602.Item(%600)> to set the values.</span></span> <span data-ttu-id="c75f5-137">A partir de C# 6, puede inicializar diccionarios y otros contenedores asociativos con la sintaxis siguiente.</span><span class="sxs-lookup"><span data-stu-id="c75f5-137">Before C# 6, you could initialize dictionaries and other associative containers using the following syntax.</span></span> <span data-ttu-id="c75f5-138">Tenga en cuenta que en lugar de sintaxis de indizador, con paréntesis y una asignación, usa un objeto con varios valores:</span><span class="sxs-lookup"><span data-stu-id="c75f5-138">Notice that instead of indexer syntax, with parentheses and an assignment, it uses an object with multiple values:</span></span>

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

<span data-ttu-id="c75f5-139">Este ejemplo de inicializador llama a <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> para agregar los tres elementos al diccionario.</span><span class="sxs-lookup"><span data-stu-id="c75f5-139">This initializer example calls <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> to add the three items into the dictionary.</span></span> <span data-ttu-id="c75f5-140">Estas dos maneras distintas de inicializar colecciones asociativas tienen un comportamiento ligeramente diferente debido a las llamadas a métodos que genera el compilador.</span><span class="sxs-lookup"><span data-stu-id="c75f5-140">These two different ways to initialize associative collections have slightly different behavior because of the method calls the compiler generates.</span></span> <span data-ttu-id="c75f5-141">Ambas variantes funcionan con la clase `Dictionary`.</span><span class="sxs-lookup"><span data-stu-id="c75f5-141">Both variants work with the `Dictionary` class.</span></span> <span data-ttu-id="c75f5-142">Es posible que otros tipos solo admitan una o la otra, en función de su API pública.</span><span class="sxs-lookup"><span data-stu-id="c75f5-142">Other types may only support one or the other based on their public API.</span></span>

## <a name="examples"></a><span data-ttu-id="c75f5-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c75f5-143">Examples</span></span>

<span data-ttu-id="c75f5-144">En el ejemplo siguiente se combinan los conceptos de inicializadores de objeto y colección.</span><span class="sxs-lookup"><span data-stu-id="c75f5-144">The following example combines the concepts of object and collection initializers.</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

<span data-ttu-id="c75f5-145">El ejemplo siguiente muestra un objeto que implementa <xref:System.Collections.IEnumerable> y que contiene un método `Add` con varios parámetros. Usa un inicializador de colección con varios elementos por cada elemento de la lista correspondiente a la firma del método `Add`.</span><span class="sxs-lookup"><span data-stu-id="c75f5-145">The following example shows an object that implements <xref:System.Collections.IEnumerable> and contains an `Add` method with multiple parameters, It uses a collection initializer with multiple elements per item in the list that correspond to the signature of the `Add` method.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

<span data-ttu-id="c75f5-146">Los métodos `Add` pueden usar la palabra clave `params` para tomar un número variable de argumentos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c75f5-146">`Add` methods can use the `params` keyword to take a variable number of arguments, as shown in the following example.</span></span> <span data-ttu-id="c75f5-147">En este ejemplo además se muestra la implementación personalizada de un indizador para inicializar una colección mediante índices.</span><span class="sxs-lookup"><span data-stu-id="c75f5-147">This example also demonstrates the custom implementation of an indexer to initialize a collection using indexes.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a><span data-ttu-id="c75f5-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="c75f5-148">See also</span></span>

- [<span data-ttu-id="c75f5-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c75f5-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c75f5-150">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="c75f5-150">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="c75f5-151">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="c75f5-151">Anonymous Types</span></span>](anonymous-types.md)
