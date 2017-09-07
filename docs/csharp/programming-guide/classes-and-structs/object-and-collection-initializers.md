---
title: "Inicializadores de objeto y de colección (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c4144f383d539129b4e03d5cad262e5a7b9e6b34
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Inicializadores de objeto y de colección (Guía de programación de C#)
Los inicializadores de objeto permiten asignar valores a cualquier campo o propiedad accesible de un objeto en el momento de su creación sin tener que invocar un constructor seguido de líneas de instrucciones de asignación. La sintaxis de inicializador de objetos permite especificar argumentos para un constructor u omitir los argumentos (y la sintaxis de paréntesis).  En el ejemplo siguiente se muestra cómo usar un inicializador de objeto con un tipo con nombre, `Cat`, y cómo invocar el constructor predeterminado. Tenga en cuenta el uso de propiedades implementadas automáticamente en la clase `Cat`. Para obtener más información, vea [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) (Propiedades implementadas automáticamente).  
  
 [!code-cs[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-cs[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)]  
  
## <a name="object-initializers-with-anonymous-types"></a>Inicializadores de objeto con tipos anónimos  
 Aunque los inicializadores de objeto se pueden usar en cualquier contexto, resultan especialmente útiles en las expresiones de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Las expresiones de consulta usan con frecuencia [tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), que solo se pueden inicializar con un inicializador de objeto, como se muestra en la siguiente declaración.  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 Los tipos anónimos permiten a la cláusula `select` de una expresión de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] transformar objetos de la secuencia original en objetos cuyo valor y forma pueden ser distintos de los originales. Esto resulta útil si desea almacenar solo una parte de la información de cada objeto en una secuencia. En el ejemplo siguiente, suponga que un objeto del producto (`p`) contiene numerosos campos y métodos y que solo le interesa crear una secuencia de objetos que contenga el nombre del producto y el precio por unidad.  
  
 [!code-cs[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
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
  
 [!code-cs[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 Puede especificar [null](../../../csharp/language-reference/keywords/null.md) como elemento de un inicializador de colección si el método `Add` de la colección lo permite.  
  
 [!code-cs[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 Puede especificar elementos indexados si la colección admite la indexación.  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

