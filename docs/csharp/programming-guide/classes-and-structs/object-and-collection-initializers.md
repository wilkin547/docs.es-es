---
title: Inicializadores de objeto y de colección (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: ad8127bfdd7178051077e6f3fe75c777acf5d345
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321953"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Inicializadores de objeto y de colección (Guía de programación de C#)
Los inicializadores de objeto permiten asignar valores a cualquier campo o propiedad accesible de un objeto en el momento de su creación sin tener que invocar un constructor seguido de líneas de instrucciones de asignación. La sintaxis de inicializador de objetos permite especificar argumentos para un constructor u omitir los argumentos (y la sintaxis de paréntesis).  En el ejemplo siguiente se muestra cómo usar un inicializador de objeto con un tipo con nombre, `Cat`, y cómo invocar el constructor predeterminado. Tenga en cuenta el uso de propiedades implementadas automáticamente en la clase `Cat`. Para obtener más información, vea [Propiedades implementadas automáticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
La sintaxis de los inicializadores de objeto le permite crear una instancia, y después asigna el objeto recién creado, con las propiedades asignadas, a la variable de la asignación.
  
## <a name="object-initializers-with-anonymous-types"></a>Inicializadores de objeto con tipos anónimos  
 Aunque los inicializadores de objeto se pueden usar en cualquier contexto, resultan especialmente útiles en las expresiones de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Las expresiones de consulta usan con frecuencia [tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), que solo se pueden inicializar con un inicializador de objeto, como se muestra en la siguiente declaración.  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 Los tipos anónimos permiten a la cláusula `select` de una expresión de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] transformar objetos de la secuencia original en objetos cuyo valor y forma pueden ser distintos de los originales. Esto resulta útil si desea almacenar solo una parte de la información de cada objeto en una secuencia. En el ejemplo siguiente, suponga que un objeto del producto (`p`) contiene numerosos campos y métodos y que solo le interesa crear una secuencia de objetos que contenga el nombre del producto y el precio por unidad.  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 Al ejecutarse esta consulta, la variable `productInfos` incluirá una secuencia de objetos a la que se puede tener acceso en una instrucción `foreach`, como se muestra en este ejemplo:  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 Cada uno de los objetos del nuevo tipo anónimo tiene dos propiedades públicas que reciben los mismos nombres que las propiedades o campos del objeto original. También puede cambiar el nombre de un campo al crear un tipo anónimo; en el ejemplo siguiente se cambia el nombre del campo `UnitPrice` a `Price`.  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a>Inicializadores de objeto con tipos que aceptan valores NULL  
 Es un error en tiempo de compilación usar un inicializador de objeto con un struct que acepta valores NULL.  
  
## <a name="collection-initializers"></a>Inicializadores de colección  
 Los inicializadores de colección le permiten especificar uno o varios inicializadores de elemento al inicializar un tipo de colección que implementa <xref:System.Collections.IEnumerable> y tiene `Add` con la firma apropiada como un método de instancia o un método de extensión. Los inicializadores de elemento pueden ser un valor simple, una expresión o un inicializador de objeto. Si se usa un inicializador de colección, no es necesario especificar varias llamadas al método `Add` de la clase en el código fuente; el compilador agrega las llamadas.  
  
 En los ejemplos siguientes se muestran dos inicializadores de colección simples:  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 El inicializador de colección siguiente usa inicializadores de objeto para inicializar los objetos de la clase `Cat` definida en un ejemplo anterior. Observe que los inicializadores de objeto individuales se escriben entre llaves y se separan por comas.  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 Puede especificar [null](../../../csharp/language-reference/keywords/null.md) como elemento de un inicializador de colección si el método `Add` de la colección lo permite.  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 Puede especificar elementos indexados si la colección admite la indexación.  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="examples"></a>Ejemplos

 En el ejemplo siguiente se combinan los conceptos de inicializadores de objeto y colección.

 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
 
 Como se muestra en el ejemplo siguiente, un objeto que implementa <xref:System.Collections.IEnumerable> y que contiene un método `Add` con varios parámetros permite inicializadores de colección con varios elementos por cada elemento de la lista correspondiente a la firma del método `Add`. 
 
 [!code-csharp[csProgGuideLINQ#84](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_7.cs)]
 
 Los métodos `Add` pueden usar la palabra clave `params` para tomar un número variable de argumentos, como se muestra en el ejemplo siguiente. En este ejemplo se muestra la implementación personalizada de un indexador también para inicializar una colección mediante índices.
 
 [!code-csharp[csProgGuideLINQ#85](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_8.cs)]
 
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
