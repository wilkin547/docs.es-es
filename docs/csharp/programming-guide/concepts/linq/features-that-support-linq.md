---
title: Características de C# compatibles con LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: 32ba8f5e60b3ed2efd813a8ae32e5f4009eb790d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202405"
---
# <a name="c-features-that-support-linq"></a>Características de C# compatibles con LINQ

La siguiente sección presenta las nuevas construcciones de lenguaje incluidas en C# 3.0. Aunque estas nuevas características se usan hasta cierto punto con consultas LINQ, no se limitan a LINQ y se pueden usar en cualquier contexto en las que se consideren de utilidad.

## <a name="query-expressions"></a>Expresiones de consulta

Las expresiones de consulta usan una sintaxis declarativa similar a SQL o XQuery para consultar colecciones de IEnumerable. En tiempo de compilación, la sintaxis de consulta se convierte en llamadas de método a la implementación de un proveedor de LINQ de los métodos de extensión de operador de consulta estándar. Las aplicaciones controlan los operadores de consulta estándar que están en el ámbito al especificar el espacio de nombres adecuado con una directiva `using`. La siguiente expresión de consulta toma una matriz de cadenas, las agrupa por el primer carácter de la cadena y ordena los grupos.

```csharp
var query = from str in stringArray
            group str by str[0] into stringGroup
            orderby stringGroup.Key
            select stringGroup;
```

Para obtener más información, vea [Expresiones de consulta LINQ](../../../linq/index.md).

## <a name="implicitly-typed-variables-var"></a>Variables con asignación implícita de tipos (var)

En lugar de especificar explícitamente un tipo al declarar e inicializar una variable, se puede usar el modificador [var](../../../language-reference/keywords/var.md) para indicar al compilador que deduzca y asigne el tipo, como se muestra aquí:

```csharp
var number = 5;
var name = "Virginia";
var query = from str in stringArray
            where str[0] == 'm'
            select str;
```

Las variables declaradas como `var` son tan fuertemente tipadas como las variables cuyo tipo se especifica explícitamente. El uso de `var` hace posible crear tipos anónimos, pero solo se puede usar para variables locales. También se pueden declarar matrices con asignación implícita de tipos.

Para más información, vea [Variables locales con asignación implícita de tipos](../../classes-and-structs/implicitly-typed-local-variables.md).

## <a name="object-and-collection-initializers"></a>Inicializadores de objeto y colección

Los inicializadores de objeto y colección permiten inicializar objetos sin llamar explícitamente a un constructor para el objeto. Los inicializadores normalmente se usan en expresiones de consulta cuando proyectan los datos de origen en un nuevo tipo de datos. Suponiendo que hay una clase denominada `Customer` con las propiedades públicas `Name` y `Phone`, el inicializador de objeto se puede usar como en el código siguiente:

```csharp
var cust = new Customer { Name = "Mike", Phone = "555-1212" };
```

Continuando con nuestra clase `Customer`, suponga que hay un origen de datos denominado `IncomingOrders` y que para cada pedido con un `OrderSize` grande, nos gustaría crear un nuevo `Customer` basado en ese orden. Se pueden ejecutar una consulta LINQ en este origen de datos y usar la inicialización de objetos para rellenar una colección:

```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```

El origen de datos puede tener más propiedades ocultas en el montón que la clase `Customer`, como `OrderSize`, pero con la inicialización de objetos, los datos devueltos por la consulta se moldean en el tipo de datos deseado; elegimos los datos que son relevantes para nuestra clase. Como resultado, ahora tenemos un `IEnumerable` relleno con el nuevo `Customer` que queríamos. Lo anterior también se puede escribir en la sintaxis de método de LINQ:

```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```

Para obtener más información, consulte:

- [Inicializadores de objeto y colección](../../classes-and-structs/object-and-collection-initializers.md)

- [Sintaxis de las expresiones de consulta para operadores de consulta estándar](./query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a>Tipos anónimos

Un tipo anónimo se construye por el compilador y el nombre del tipo solo está disponible para el compilador. Los tipos anónimos son una manera cómoda de agrupar un conjunto de propiedades temporalmente en un resultado de consulta sin tener que definir un tipo con nombre independiente. Los tipos anónimos se inicializan con una nueva expresión y un inicializador de objeto, como se muestra aquí:

```csharp
select new {name = cust.Name, phone = cust.Phone};
```

Para obtener más información, vea [Tipos anónimos](../../classes-and-structs/anonymous-types.md).

## <a name="extension-methods"></a>Métodos de extensión.

Un método de extensión es un método estático que se puede asociar con un tipo, por lo que puede llamarse como si fuera un método de instancia en el tipo. Esta característica permite, en efecto, "agregar" nuevos métodos a los tipos existentes sin tener que modificarlos realmente. Los operadores de consulta estándar son un conjunto de métodos de extensión que proporcionan funciones de consultas LINQ para cualquier tipo que implemente <xref:System.Collections.Generic.IEnumerable%601>.

Para obtener más información, vea [Métodos de extensión](../../classes-and-structs/extension-methods.md).

## <a name="lambda-expressions"></a>Expresiones lambda

Una expresión lambda es una función insertada que usa el operador => para separar los parámetros de entrada del cuerpo de la función y que se puede convertir en tiempo de compilación en un delegado o un árbol de expresión. En la programación de LINQ, encontrará expresiones lambda al realizar llamadas de método directas a los operadores de consulta estándar.

Para obtener más información, consulte:

- [Funciones anónimas](../../statements-expressions-operators/anonymous-functions.md)

- [Expresiones lambda](../../statements-expressions-operators/lambda-expressions.md)

- [Árboles de expresión (C#)](../expression-trees/index.md)

## <a name="see-also"></a>Vea también

- [Language Integrated Query (LINQ) (C#)](./index.md)
