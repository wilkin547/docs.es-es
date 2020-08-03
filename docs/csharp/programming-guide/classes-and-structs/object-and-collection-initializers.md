---
title: 'Inicializadores de objeto y de colección: Guía de programación de C#'
description: Los inicializadores de objeto en C# asignan valores a campos o propiedades accesibles de un objeto durante la creación después de invocar un constructor.
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 81deed8a21bff10364524c3e0784c562d4e727e6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864779"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Inicializadores de objeto y de colección (Guía de programación de C#)

C# permite crear instancias de un objeto o colección y realizar asignaciones de miembros en una sola instrucción.

## <a name="object-initializers"></a>Inicializadores de objeto

Los inicializadores de objeto permiten asignar valores a cualquier campo o propiedad accesible de un objeto en el momento de su creación sin tener que invocar un constructor seguido de líneas de instrucciones de asignación. La sintaxis de inicializador de objetos permite especificar argumentos para un constructor u omitir los argumentos (y la sintaxis de paréntesis).  En el ejemplo siguiente se muestra cómo usar un inicializador de objeto con un tipo con nombre, `Cat`, y cómo invocar el constructor sin parámetros. Tenga en cuenta el uso de propiedades implementadas automáticamente en la clase `Cat`. Para obtener más información, vea [Propiedades implementadas automáticamente](auto-implemented-properties.md).  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  

La sintaxis de los inicializadores de objeto le permite crear una instancia, y después asigna el objeto recién creado, con las propiedades asignadas, a la variable de la asignación.

A partir de C# 6, los inicializadores de objeto pueden establecer indizadores, además de asignar campos y propiedades. Tenga en cuenta esta clase básica `Matrix`:

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

Se podría inicializar la matriz de identidad con el código siguiente:

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

Puede usarse cualquier indizador accesible que contenga un establecedor accesible como una de las expresiones de un inicializador de objeto, independientemente del número o los tipos de argumentos. Los argumentos del índice forman el lado izquierdo de la asignación, mientras que el valor es el lado derecho de la expresión.  Por ejemplo, todos estos son válidos si `IndexersExample` tiene los indizadores adecuados:

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

Para que el código anterior se compile, el tipo `IndexersExample` debe tener los siguientes miembros:

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a>Inicializadores de objeto con tipos anónimos

Aunque los inicializadores de objeto se pueden usar en cualquier contexto, resultan especialmente útiles en las expresiones de consulta LINQ. Las expresiones de consulta usan con frecuencia [tipos anónimos](./anonymous-types.md), que solo se pueden inicializar con un inicializador de objeto, como se muestra en la siguiente declaración.  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

Los tipos anónimos permiten a la cláusula `select` de una expresión de consulta LINQ transformar objetos de la secuencia original en objetos cuyo valor y forma pueden ser distintos de los originales. Esto resulta útil si desea almacenar solo una parte de la información de cada objeto en una secuencia. En el ejemplo siguiente, suponga que un objeto del producto (`p`) contiene numerosos campos y métodos y que solo le interesa crear una secuencia de objetos que contenga el nombre del producto y el precio por unidad.  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

Al ejecutarse esta consulta, la variable `productInfos` incluirá una secuencia de objetos a la que se puede tener acceso en una instrucción `foreach`, como se muestra en este ejemplo:  

```csharp
foreach(var p in productInfos){...}  
```

Cada objeto del nuevo tipo anónimo tiene dos propiedades públicas que reciben los mismos nombres que las propiedades o los campos del objeto original. También puede cambiar el nombre de un campo al crear un tipo anónimo; en el ejemplo siguiente se cambia el nombre del campo `UnitPrice` a `Price`.  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a>Inicializadores de colección

Los inicializadores de colección le permiten especificar uno o varios inicializadores de elemento al inicializar un tipo de colección que implementa <xref:System.Collections.IEnumerable> y tiene `Add` con la firma apropiada como un método de instancia o un método de extensión. Los inicializadores de elemento pueden ser un valor simple, una expresión o un inicializador de objeto. Si se usa un inicializador de colección, no es necesario especificar varias llamadas; el compilador las agrega automáticamente.  
  
En el ejemplo siguiente se muestran dos inicializadores de colección simples:  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

El inicializador de colección siguiente usa inicializadores de objeto para inicializar los objetos de la clase `Cat` definida en un ejemplo anterior. Observe que los inicializadores de objeto individuales se escriben entre llaves y se separan por comas.  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
Puede especificar [null](../../language-reference/keywords/null.md) como elemento de un inicializador de colección si el método `Add` de la colección lo permite.  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 Puede especificar elementos indexados si la colección admite indexación de lectura y escritura.
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

El ejemplo anterior genera código que llama a <xref:System.Collections.Generic.Dictionary%602.Item(%600)> para establecer los valores. A partir de C# 6, puede inicializar diccionarios y otros contenedores asociativos con la sintaxis siguiente. Tenga en cuenta que en lugar de sintaxis de indizador, con paréntesis y una asignación, usa un objeto con varios valores:

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

Este ejemplo de inicializador llama a <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> para agregar los tres elementos al diccionario. Estas dos maneras distintas de inicializar colecciones asociativas tienen un comportamiento ligeramente diferente debido a las llamadas a métodos que genera el compilador. Ambas variantes funcionan con la clase `Dictionary`. Es posible que otros tipos solo admitan una o la otra, en función de su API pública.

## <a name="examples"></a>Ejemplos

En el ejemplo siguiente se combinan los conceptos de inicializadores de objeto y colección.

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

El ejemplo siguiente muestra un objeto que implementa <xref:System.Collections.IEnumerable> y que contiene un método `Add` con varios parámetros. Usa un inicializador de colección con varios elementos por cada elemento de la lista correspondiente a la firma del método `Add`.

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

Los métodos `Add` pueden usar la palabra clave `params` para tomar un número variable de argumentos, como se muestra en el ejemplo siguiente. En este ejemplo además se muestra la implementación personalizada de un indizador para inicializar una colección mediante índices.

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [LINQ en C#](../../linq/index.md)
- [Tipos anónimos](anonymous-types.md)
