---
title: Características de C# compatibles con LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: c617b2d7b56618867fe92cbe1d9ee04aa4c3ab64
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207244"
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="24071-102">Características de C# compatibles con LINQ</span><span class="sxs-lookup"><span data-stu-id="24071-102">C# Features That Support LINQ</span></span>
<span data-ttu-id="24071-103">La siguiente sección presenta las nuevas construcciones de lenguaje incluidas en C# 3.0.</span><span class="sxs-lookup"><span data-stu-id="24071-103">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="24071-104">Aunque estas nuevas características se usan hasta cierto punto con consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], no se limitan a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] y se pueden usar en cualquier contexto en las que se consideren de utilidad.</span><span class="sxs-lookup"><span data-stu-id="24071-104">Although these new features are all used to a degree with [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, they are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] and can be used in any context where you find them useful.</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="24071-105">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="24071-105">Query Expressions</span></span>  
 <span data-ttu-id="24071-106">Las expresiones de consulta usan una sintaxis declarativa similar a SQL o XQuery para consultar colecciones de IEnumerable.</span><span class="sxs-lookup"><span data-stu-id="24071-106">Query expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="24071-107">En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a la implementación de un proveedor de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] de los métodos de extensión de operador de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="24071-107">At compile time query syntax is converted to method calls to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="24071-108">Las aplicaciones controlan los operadores de consulta estándar que están en el ámbito al especificar el espacio de nombres adecuado con una directiva `using`.</span><span class="sxs-lookup"><span data-stu-id="24071-108">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="24071-109">La siguiente expresión de consulta toma una matriz de cadenas, las agrupa por el primer carácter de la cadena y ordena los grupos.</span><span class="sxs-lookup"><span data-stu-id="24071-109">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>  
  
```csharp  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 <span data-ttu-id="24071-110">Para obtener más información, vea [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span><span class="sxs-lookup"><span data-stu-id="24071-110">For more information, see [LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span></span>  
  
## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="24071-111">Variables con asignación implícita de tipos (var)</span><span class="sxs-lookup"><span data-stu-id="24071-111">Implicitly Typed Variables (var)</span></span>  
 <span data-ttu-id="24071-112">En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, se puede usar el modificador [var](../../../../csharp/language-reference/keywords/var.md) para indicar al compilador que deduzca y asigne el tipo, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="24071-112">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../../csharp/language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>  
  
```csharp  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 <span data-ttu-id="24071-113">Las variables declaradas como `var` son tan fuertemente tipadas como las variables cuyo tipo se especifica explícitamente.</span><span class="sxs-lookup"><span data-stu-id="24071-113">Variables declared as `var` are just as strongly-typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="24071-114">El uso de `var` hace posible crear tipos anónimos, pero solo se puede usar para variables locales.</span><span class="sxs-lookup"><span data-stu-id="24071-114">The use of `var` makes it possible to create anonymous types, but it can be used only for local variables.</span></span> <span data-ttu-id="24071-115">También se pueden declarar matrices con asignación implícita de tipos.</span><span class="sxs-lookup"><span data-stu-id="24071-115">Arrays can also be declared with implicit typing.</span></span>  
  
 <span data-ttu-id="24071-116">Para más información, vea [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="24071-116">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="object-and-collection-initializers"></a><span data-ttu-id="24071-117">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="24071-117">Object and Collection Initializers</span></span>  
 <span data-ttu-id="24071-118">Los inicializadores de objeto y colección permiten inicializar objetos sin llamar explícitamente a un constructor para el objeto.</span><span class="sxs-lookup"><span data-stu-id="24071-118">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="24071-119">Los inicializadores normalmente se usan en expresiones de consulta cuando proyectan los datos de origen en un nuevo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="24071-119">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="24071-120">Suponiendo que hay una clase denominada `Customer` con las propiedades públicas `Name` y `Phone`, el inicializador de objeto se puede usar como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="24071-120">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>  
  
```csharp  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 <span data-ttu-id="24071-121">Para más información, vea [Inicializadores de objeto y de colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="24071-121">For more information, see [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="24071-122">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="24071-122">Anonymous Types</span></span>  
 <span data-ttu-id="24071-123">Un tipo anónimo se construye por el compilador y el nombre del tipo solo está disponible para el compilador.</span><span class="sxs-lookup"><span data-stu-id="24071-123">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="24071-124">Los tipos anónimos son una manera cómoda de agrupar un conjunto de propiedades temporalmente en un resultado de consulta sin tener que definir un tipo con nombre independiente.</span><span class="sxs-lookup"><span data-stu-id="24071-124">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="24071-125">Los tipos anónimos se inicializan con una nueva expresión y un inicializador de objeto, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="24071-125">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 <span data-ttu-id="24071-126">Para obtener más información, vea [Tipos anónimos](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="24071-126">For more information, see [Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="24071-127">Métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="24071-127">Extension Methods</span></span>  
 <span data-ttu-id="24071-128">Un método de extensión es un método estático que se puede asociar con un tipo, por lo que puede llamarse como si fuera un método de instancia en el tipo.</span><span class="sxs-lookup"><span data-stu-id="24071-128">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="24071-129">Esta característica permite, en efecto, "agregar" nuevos métodos a los tipos existentes sin tener que modificarlos realmente.</span><span class="sxs-lookup"><span data-stu-id="24071-129">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="24071-130">Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan funciones de consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="24071-130">The standard query operators are a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="24071-131">Para más información, vea [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="24071-131">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="24071-132">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="24071-132">Lambda Expressions</span></span>  
 <span data-ttu-id="24071-133">Una expresión lambda es una función insertada que usa el operador => para separar los parámetros de entrada del cuerpo de la función y que se puede convertir en tiempo de compilación en un delegado o un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="24071-133">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="24071-134">En la programación de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], encontrará expresiones lambda al realizar llamadas de método directas a los operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="24071-134">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>  
  
 <span data-ttu-id="24071-135">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="24071-135">For more information, see:</span></span>  
  
-   [<span data-ttu-id="24071-136">Funciones anónimas</span><span class="sxs-lookup"><span data-stu-id="24071-136">Anonymous Functions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="24071-137">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="24071-137">Lambda Expressions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [<span data-ttu-id="24071-138">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="24071-138">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a><span data-ttu-id="24071-139">Propiedades autoimplementadas</span><span class="sxs-lookup"><span data-stu-id="24071-139">Auto-Implemented Properties</span></span>  
 <span data-ttu-id="24071-140">Las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa.</span><span class="sxs-lookup"><span data-stu-id="24071-140">Auto-implemented properties make property-declaration more concise.</span></span> <span data-ttu-id="24071-141">Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede tener acceso con el captador y el establecedor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="24071-141">When you declare a property as shown in the following example, the compiler will create a private, anonymous backing field that is not accessible except through the property getter and setter.</span></span>  
  
```csharp  
public string Name {get; set;}  
```  
  
 <span data-ttu-id="24071-142">Para obtener más información, vea [Propiedades implementadas automáticamente](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="24071-142">For more information, see [Auto-Implemented Properties](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24071-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="24071-143">See Also</span></span>

- [<span data-ttu-id="24071-144">Language-Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="24071-144">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
