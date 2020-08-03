---
title: Características de C# compatibles con LINQ
description: Obtenga información sobre características de C# que se usan con consultas de LINQ y en otros contextos. Estas construcciones de lenguaje se han incorporado en C# 3.0.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: f72b82180d794086dcea9f11a7a057dc26ab0b26
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105424"
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="612c7-104">Características de C# compatibles con LINQ</span><span class="sxs-lookup"><span data-stu-id="612c7-104">C# Features That Support LINQ</span></span>

<span data-ttu-id="612c7-105">La siguiente sección presenta las nuevas construcciones de lenguaje incluidas en C# 3.0.</span><span class="sxs-lookup"><span data-stu-id="612c7-105">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="612c7-106">Aunque estas nuevas características se usan hasta cierto punto con consultas LINQ, no se limitan a LINQ y se pueden usar en cualquier contexto en las que se consideren de utilidad.</span><span class="sxs-lookup"><span data-stu-id="612c7-106">Although these new features are all used to a degree with LINQ queries, they are not limited to LINQ and can be used in any context where you find them useful.</span></span>

## <a name="query-expressions"></a><span data-ttu-id="612c7-107">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="612c7-107">Query Expressions</span></span>

<span data-ttu-id="612c7-108">Las expresiones de consulta usan una sintaxis declarativa similar a SQL o XQuery para consultar colecciones de IEnumerable.</span><span class="sxs-lookup"><span data-stu-id="612c7-108">Query expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="612c7-109">En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a la implementación de un proveedor de LINQ de los métodos de extensión de operador de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="612c7-109">At compile time query syntax is converted to method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="612c7-110">Las aplicaciones controlan los operadores de consulta estándar que están en el ámbito al especificar el espacio de nombres adecuado con una directiva `using`.</span><span class="sxs-lookup"><span data-stu-id="612c7-110">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="612c7-111">La siguiente expresión de consulta toma una matriz de cadenas, las agrupa por el primer carácter de la cadena y ordena los grupos.</span><span class="sxs-lookup"><span data-stu-id="612c7-111">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>

```csharp
var query = from str in stringArray
            group str by str[0] into stringGroup
            orderby stringGroup.Key
            select stringGroup;
```

<span data-ttu-id="612c7-112">Para obtener más información, vea [Expresiones de consulta LINQ](../../../linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="612c7-112">For more information, see [LINQ Query Expressions](../../../linq/index.md).</span></span>

## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="612c7-113">Variables con asignación implícita de tipos (var)</span><span class="sxs-lookup"><span data-stu-id="612c7-113">Implicitly Typed Variables (var)</span></span>

<span data-ttu-id="612c7-114">En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, se puede usar el modificador [var](../../../language-reference/keywords/var.md) para indicar al compilador que deduzca y asigne el tipo, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="612c7-114">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>

```csharp
var number = 5;
var name = "Virginia";
var query = from str in stringArray
            where str[0] == 'm'
            select str;
```

<span data-ttu-id="612c7-115">Las variables declaradas como `var` son tan fuertemente tipadas como las variables cuyo tipo se especifica explícitamente.</span><span class="sxs-lookup"><span data-stu-id="612c7-115">Variables declared as `var` are just as strongly typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="612c7-116">El uso de `var` hace posible crear tipos anónimos, pero solo se puede usar para variables locales.</span><span class="sxs-lookup"><span data-stu-id="612c7-116">The use of `var` makes it possible to create anonymous types, but it can be used only for local variables.</span></span> <span data-ttu-id="612c7-117">También se pueden declarar matrices con asignación implícita de tipos.</span><span class="sxs-lookup"><span data-stu-id="612c7-117">Arrays can also be declared with implicit typing.</span></span>

<span data-ttu-id="612c7-118">Para más información, vea [Variables locales con asignación implícita de tipos](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="612c7-118">For more information, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

## <a name="object-and-collection-initializers"></a><span data-ttu-id="612c7-119">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="612c7-119">Object and Collection Initializers</span></span>

<span data-ttu-id="612c7-120">Los inicializadores de objeto y colección permiten inicializar objetos sin llamar explícitamente a un constructor para el objeto.</span><span class="sxs-lookup"><span data-stu-id="612c7-120">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="612c7-121">Los inicializadores normalmente se usan en expresiones de consulta cuando proyectan los datos de origen en un nuevo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="612c7-121">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="612c7-122">Suponiendo que hay una clase denominada `Customer` con las propiedades públicas `Name` y `Phone`, el inicializador de objeto se puede usar como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="612c7-122">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>

```csharp
var cust = new Customer { Name = "Mike", Phone = "555-1212" };
```

<span data-ttu-id="612c7-123">Continuando con nuestra clase `Customer`, suponga que hay un origen de datos denominado `IncomingOrders` y que para cada pedido con un `OrderSize` grande, nos gustaría crear un nuevo `Customer` basado en ese orden.</span><span class="sxs-lookup"><span data-stu-id="612c7-123">Continuing with our `Customer` class, assume that there is a data source called `IncomingOrders`, and that for each order with a large `OrderSize`, we would like to create a new `Customer` based off of that order.</span></span> <span data-ttu-id="612c7-124">Se pueden ejecutar una consulta LINQ en este origen de datos y usar la inicialización de objetos para rellenar una colección:</span><span class="sxs-lookup"><span data-stu-id="612c7-124">A LINQ query can be executed on this data source and use object initialization to fill a collection:</span></span>

```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```

<span data-ttu-id="612c7-125">El origen de datos puede tener más propiedades ocultas en el montón que la clase `Customer`, como `OrderSize`, pero con la inicialización de objetos, los datos devueltos por la consulta se moldean en el tipo de datos deseado; elegimos los datos que son relevantes para nuestra clase.</span><span class="sxs-lookup"><span data-stu-id="612c7-125">The data source may have more properties lying under the hood than the `Customer` class such as `OrderSize`, but with object initialization, the data returned from the query is molded into the desired data type; we choose the data that is relevant to our class.</span></span> <span data-ttu-id="612c7-126">Como resultado, ahora tenemos un `IEnumerable` relleno con el nuevo `Customer` que queríamos.</span><span class="sxs-lookup"><span data-stu-id="612c7-126">As a result, we now have an `IEnumerable` filled with the new `Customer`s we wanted.</span></span> <span data-ttu-id="612c7-127">Lo anterior también se puede escribir en la sintaxis de método de LINQ:</span><span class="sxs-lookup"><span data-stu-id="612c7-127">The above can also be written in LINQ's method syntax:</span></span>

```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```

<span data-ttu-id="612c7-128">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="612c7-128">For more information, see:</span></span>

- [<span data-ttu-id="612c7-129">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="612c7-129">Object and Collection Initializers</span></span>](../../classes-and-structs/object-and-collection-initializers.md)

- [<span data-ttu-id="612c7-130">Sintaxis de las expresiones de consulta para operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="612c7-130">Query Expression Syntax for Standard Query Operators</span></span>](./query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a><span data-ttu-id="612c7-131">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="612c7-131">Anonymous Types</span></span>

<span data-ttu-id="612c7-132">Un tipo anónimo se construye por el compilador y el nombre del tipo solo está disponible para el compilador.</span><span class="sxs-lookup"><span data-stu-id="612c7-132">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="612c7-133">Los tipos anónimos son una manera cómoda de agrupar un conjunto de propiedades temporalmente en un resultado de consulta sin tener que definir un tipo con nombre independiente.</span><span class="sxs-lookup"><span data-stu-id="612c7-133">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="612c7-134">Los tipos anónimos se inicializan con una nueva expresión y un inicializador de objeto, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="612c7-134">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>

```csharp
select new {name = cust.Name, phone = cust.Phone};
```

<span data-ttu-id="612c7-135">Para obtener más información, vea [Tipos anónimos](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="612c7-135">For more information, see [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>

## <a name="extension-methods"></a><span data-ttu-id="612c7-136">Métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="612c7-136">Extension Methods</span></span>

<span data-ttu-id="612c7-137">Un método de extensión es un método estático que se puede asociar con un tipo, por lo que puede llamarse como si fuera un método de instancia en el tipo.</span><span class="sxs-lookup"><span data-stu-id="612c7-137">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="612c7-138">Esta característica permite, en efecto, "agregar" nuevos métodos a los tipos existentes sin tener que modificarlos realmente.</span><span class="sxs-lookup"><span data-stu-id="612c7-138">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="612c7-139">Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan funciones de consultas LINQ para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="612c7-139">The standard query operators are a set of extension methods that provide LINQ query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>

<span data-ttu-id="612c7-140">Para obtener más información, vea [Métodos de extensión](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="612c7-140">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="lambda-expressions"></a><span data-ttu-id="612c7-141">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="612c7-141">Lambda Expressions</span></span>

<span data-ttu-id="612c7-142">Una expresión lambda es una función insertada que usa el operador => para separar los parámetros de entrada del cuerpo de la función y que se puede convertir en tiempo de compilación en un delegado o un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="612c7-142">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="612c7-143">En la programación de LINQ, encontrará expresiones lambda al realizar llamadas de método directas a los operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="612c7-143">In LINQ programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>

<span data-ttu-id="612c7-144">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="612c7-144">For more information, see:</span></span>

- [<span data-ttu-id="612c7-145">Funciones anónimas</span><span class="sxs-lookup"><span data-stu-id="612c7-145">Anonymous Functions</span></span>](../../statements-expressions-operators/anonymous-functions.md)

- [<span data-ttu-id="612c7-146">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="612c7-146">Lambda Expressions</span></span>](../../statements-expressions-operators/lambda-expressions.md)

- [<span data-ttu-id="612c7-147">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="612c7-147">Expression Trees (C#)</span></span>](../expression-trees/index.md)

## <a name="see-also"></a><span data-ttu-id="612c7-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="612c7-148">See also</span></span>

- [<span data-ttu-id="612c7-149">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="612c7-149">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
