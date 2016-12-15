---
title: "Inicializadores de objeto y de colecci&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "inicializadores de colección [C#]"
  - "inicializadores de objeto [C#]"
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Inicializadores de objeto y de colecci&#243;n (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los inicializadores de objeto permiten asignar valores a cualquier campo o propiedad accesible de un objeto en el momento de su creación sin tener que invocar un constructor seguido de líneas de instrucciones de asignación.  La sintaxis de inicializador de objetos permite especificar argumentos para un constructor u omitir los argumentos \(y la sintaxis de paréntesis\).  En el ejemplo siguiente se muestra cómo usar un inicializador de objeto con un tipo con nombre, `Cat`, y cómo invocar el constructor predeterminado.  Tenga en cuenta el uso de propiedades implementadas automáticamente en la clase `Cat`.  Para obtener más información, vea [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
 [!code-cs[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-cs[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)]  
  
## Inicializadores de objeto con tipos anónimos  
 Aunque los inicializadores de objeto se pueden usar en cualquier contexto, son especialmente útiles en las expresiones de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)].  Las expresiones de consulta usan con frecuencia [tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), que solo se pueden inicializar con un inicializador de objeto, como se muestra en la siguiente declaración.  
  
```  
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 Los tipos anónimos permiten a la cláusula `select` de una expresión de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] transformar objetos de la secuencia original en objetos cuyo valor y forma pueden ser distintos de los originales.  Esto resulta útil si desea almacenar solo una parte de la información de cada objeto en una secuencia.  En el ejemplo siguiente, suponga que un objeto del producto \(`p`\) contiene numerosos campos y métodos y que solo le interesa crear una secuencia de objetos que contenga el nombre del producto y el precio por unidad.  
  
 [!code-cs[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 Al ejecutarse esta consulta, la variable `productInfos` incluirá una secuencia de objetos a la que se puede tener acceso en una instrucción `foreach`, como se muestra en este ejemplo:  
  
```  
foreach(var p in productInfos){...}  
```  
  
 Cada uno de los objetos del nuevo tipo anónimo tiene dos propiedades públicas que reciben los mismos nombres que las propiedades o campos del objeto original.  También puede cambiar el nombre de un campo al crear un tipo anónimo; en el ejemplo siguiente se cambia el nombre del campo `UnitPrice` a `Price`.  
  
```  
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## Inicializadores de objeto con tipos que aceptan valores NULL  
 Es un error en tiempo de compilación usar un inicializador de objeto con un struct que acepta valores NULL.  
  
## Inicializadores de colección  
 Los inicializadores de colección le permiten especificar uno o varios inicializadores de elemento al inicializar una clase de colección que implementa <xref:System.Collections.IEnumerable> o una clase con un método de extensión de `Add`.  Los inicializadores de elemento pueden ser un valor simple, una expresión o un inicializador de objeto.  Si se usa un inicializador de colección, no es necesario especificar varias llamadas al método `Add` de la clase en el código fuente; el compilador agrega las llamadas.  
  
 En los ejemplos siguientes se muestran dos inicializadores de colección simples:  
  
```  
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 El inicializador de colección siguiente usa inicializadores de objeto para inicializar los objetos de la clase `Cat` definida en un ejemplo anterior.  Observe que los inicializadores de objeto individuales se escriben entre llaves y se separan por comas.  
  
 [!code-cs[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 Puede especificar [NULL](../../../csharp/language-reference/keywords/null.md) como elemento de un inicializador de colección si el método `Add` de la colección lo permite.  
  
 [!code-cs[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 Puede especificar elementos indexados si la colección admite la indexación.  
  
```  
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
  
```  
  
## Ejemplo  
 [!code-cs[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)