---
title: Language-Integrated Query (LINQ) (C#)
ms.date: 02/02/2017
ms.assetid: 19dd1782-905b-4a9d-a3e9-618453037fa2
ms.openlocfilehash: c19e0eb658c428a3e511251f4851868de676d887
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="language-integrated-query-linq"></a>Language-Integrated Query (LINQ)

Language-Integrated Query (LINQ) es el nombre de un conjunto de tecnologías basadas en la integración de capacidades de consulta directamente en el lenguaje C#. Tradicionalmente, las consultas con datos se expresaban como cadenas simples sin comprobación de tipos en tiempo de compilación ni compatibilidad con IntelliSense. Además, tiene que aprender un lenguaje de consultas diferente para cada tipo de origen de datos: bases de datos SQL, documentos XML y varios servicios web, entre otros. Con LINQ, una consulta es una construcción de lenguaje de primera clase, como clases, métodos y eventos.

Para un desarrollador que escribe consultas, la parte más visible de "lenguaje integrado" de LINQ es la expresión de consulta. Las expresiones de consulta se escriben con una *sintaxis de consulta* declarativa. Con la sintaxis de consulta, puede realizar operaciones de filtrado, ordenación y agrupamiento en orígenes de datos con el mínimo código. Utilice los mismos patrones de expresión de consulta básica para consultar y transformar datos de bases de datos SQL, conjuntos de datos de ADO .NET, secuencias y documentos XML y colecciones. NET.

En el ejemplo siguiente se muestra la operación de consulta completa. La operación completa incluye crear un origen de datos, definir la expresión de consulta y ejecutar la consulta en una instrucción `foreach`.

[!code-csharp[csProgGuideLINQ#11](../../../../../samples/snippets/csharp/concepts/linq/index_1.cs)]

## <a name="query-expression-overview"></a>Información general sobre la expresión de consulta

-   Las expresiones de consulta se pueden utilizar para consultar y transformar los datos de cualquier origen de datos habilitado para LINQ. Por ejemplo, una sola consulta puede recuperar datos de una base de datos SQL y generar una secuencia XML como salida.  
  
-   Las expresiones de consulta son fáciles de controlar porque utilizan muchas construcciones de lenguaje C# familiares.  
  
-   Todas las variables de una expresión de consulta están fuertemente tipadas, aunque en muchos casos no es necesario proporcionar el tipo explícitamente porque el compilador puede deducirlo. Para más información, vea [Type Relationships in LINQ Query Operations](type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta LINQ).  
  
-   Una consulta no se ejecuta hasta que no se realiza la iteración a través de la variable de consulta, por ejemplo, en una instrucción `foreach`. Para más información, vea [Introduction to LINQ queries](introduction-to-linq-queries.md) (Introducción a las consultas LINQ).  
  
-   En tiempo de compilación, las expresiones de consulta se convierten en llamadas al método de operador de consulta estándar según las reglas establecidas en la especificación de C#. Cualquier consulta que se puede expresar con sintaxis de consulta también se puede expresar mediante sintaxis de método. Sin embargo, en la mayoría de los casos, la sintaxis de consulta es más legible y concisa. Para más información, vea [Especificación del lenguaje C#](../../../language-reference/language-specification/index.md) e [Información general sobre operadores de consulta estándar](standard-query-operators-overview.md).  
  
-   Como regla al escribir consultas LINQ, se recomienda utilizar la sintaxis de consulta siempre que sea posible y la sintaxis de método cuando sea necesario. No hay diferencias semánticas ni de rendimiento entre estas dos formas diversas. Las expresiones de consulta suelen ser más legibles que las expresiones equivalentes escritas con la sintaxis de método.  
  
-   Algunas operaciones de consulta, como <xref:System.Linq.Enumerable.Count%2A> o <xref:System.Linq.Enumerable.Max%2A>, no tienen ninguna cláusula de expresión de consulta equivalente, de modo que deben expresarse como una llamada de método. La sintaxis de método se puede combinar con la sintaxis de consulta de varias maneras. Para más información, vea [Query syntax and method syntax in LINQ](query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consulta y sintaxis de método en LINQ).  
  
-   Las expresiones de consulta pueden compilarse en árboles de expresión o en delegados, en función del tipo al que se aplica la consulta. Las consultas <xref:System.Collections.Generic.IEnumerable%601> se compilan en delegados. Las consultas <xref:System.Linq.IQueryable> y <xref:System.Linq.IQueryable%601> se compilan en árboles de expresión. Para más información, vea [Expression trees](../../../expression-trees.md) (Árboles de expresión).  

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre LINQ, empiece a familiarizarse con algunos conceptos básicos en [Conceptos básicos de las expresiones de consultas](../../../linq/query-expression-basics.md) y, después, lea la documentación de la tecnología de LINQ en la que esté interesado:   
-   Documentos XML: [LINQ to XML](linq-to-xml.md) (LINQ para XML)  
  
-   ADO.NET Entity Framework: [LINQ to entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) (LINQ para entidades)  
  
-   Colecciones .NET, archivos y cadenas, entre otros: [LINQ to objects](linq-to-objects.md) (LINQ para objetos)

Para comprender mejor los aspectos generales de LINQ, vea [LINQ in C#](../../../linq/linq-in-csharp.md) (LINQ en C#).

Para empezar a trabajar con LINQ en C#, vea el tutorial [Working with LINQ](../../../tutorials/working-with-linq.md) (Trabajar con LINQ).



