---
title: Language-Integrated Query (LINQ) (C#)
description: Obtenga información sobre las consultas Language-Integrated Queries (LINQ) y consulte un ejemplo de una operación de consulta completa.
ms.date: 02/02/2017
ms.assetid: 19dd1782-905b-4a9d-a3e9-618453037fa2
ms.openlocfilehash: 967f69e94b0424e208fb675a312ab306d5e11842
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556738"
---
# <a name="language-integrated-query-linq"></a>Language-Integrated Query (LINQ)

Language-Integrated Query (LINQ) es el nombre de un conjunto de tecnologías basadas en la integración de capacidades de consulta directamente en el lenguaje C#. Tradicionalmente, las consultas con datos se expresaban como cadenas simples sin comprobación de tipos en tiempo de compilación ni compatibilidad con IntelliSense. Además, tendrá que aprender un lenguaje de consulta diferente para cada tipo de origen de datos: bases de datos SQL, documentos XML, varios servicios web y así sucesivamente. Con LINQ, una consulta es una construcción de lenguaje de primera clase, como clases, métodos y eventos. Escribe consultas en colecciones de objetos fuertemente tipadas con palabras clave del lenguaje y operadores familiares. La familia de tecnologías de LINQ proporciona una experiencia de consulta coherente para objetos (LINQ to Objects), bases de datos relacionales (LINQ to SQL) y XML (LINQ to XML).

Para un desarrollador que escribe consultas, la parte más visible de "lenguaje integrado" de LINQ es la expresión de consulta. Las expresiones de consulta se escriben con una *sintaxis de consulta* declarativa. Con la sintaxis de consulta, puede realizar operaciones de filtrado, ordenación y agrupamiento en orígenes de datos con el mínimo código. Utilice los mismos patrones de expresión de consulta básica para consultar y transformar datos de bases de datos SQL, conjuntos de datos de ADO .NET, secuencias y documentos XML y colecciones. NET.

Puede escribir consultas LINQ en C# para bases de datos de SQL Server, documentos XML, conjuntos de datos ADO.NET y cualquier colección de objetos que admita <xref:System.Collections.IEnumerable> o la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>. La compatibilidad con LINQ también se proporciona por terceros para muchos servicios web y otras implementaciones de base de datos.

En el ejemplo siguiente se muestra la operación de consulta completa. La operación completa incluye crear un origen de datos, definir la expresión de consulta y ejecutar la consulta en una instrucción `foreach`.

[!code-csharp[csProgGuideLINQ#11](~/samples/snippets/csharp/concepts/linq/index_1.cs)]

En la siguiente ilustración de Visual Studio se muestra una consulta LINQ parcialmente completa en una base de datos de SQL Server en C# y Visual Basic con la comprobación de tipos completa y la compatibilidad con IntelliSense:

![Diagrama en el que se muestra una consulta LINQ con IntelliSense.](./media/introduction-to-linq/linq-query-intellisense.png)

## <a name="query-expression-overview"></a>Información general sobre la expresión de consulta

- Las expresiones de consulta se pueden utilizar para consultar y transformar los datos de cualquier origen de datos habilitado para LINQ. Por ejemplo, una sola consulta puede recuperar datos de una base de datos SQL y generar una secuencia XML como salida.
- Las expresiones de consulta son fáciles de controlar porque utilizan muchas construcciones de lenguaje C# familiares.
- Todas las variables de una expresión de consulta están fuertemente tipadas, aunque en muchos casos no es necesario proporcionar el tipo explícitamente porque el compilador puede deducirlo. Para más información, vea [Relaciones entre tipos en operaciones de consulta LINQ](type-relationships-in-linq-query-operations.md).
- Una consulta no se ejecuta hasta que no se realiza la iteración a través de la variable de consulta, por ejemplo, en una instrucción `foreach`. Para más información, vea [Introducción a las consultas LINQ](introduction-to-linq-queries.md).
- En tiempo de compilación, las expresiones de consulta se convierten en llamadas al método de operador de consulta estándar según las reglas establecidas en la especificación de C#. Cualquier consulta que se puede expresar con sintaxis de consulta también se puede expresar mediante sintaxis de método. Sin embargo, en la mayoría de los casos, la sintaxis de consulta es más legible y concisa. Para más información, vea [Especificación del lenguaje C#](~/_csharplang/spec/expressions.md#query-expressions) e [Información general sobre operadores de consulta estándar](standard-query-operators-overview.md).
- Como regla al escribir consultas LINQ, se recomienda utilizar la sintaxis de consulta siempre que sea posible y la sintaxis de método cuando sea necesario. No hay diferencias semánticas ni de rendimiento entre estas dos formas diversas. Las expresiones de consulta suelen ser más legibles que las expresiones equivalentes escritas con la sintaxis de método.
- Algunas operaciones de consulta, como <xref:System.Linq.Enumerable.Count%2A> o <xref:System.Linq.Enumerable.Max%2A>, no tienen ninguna cláusula de expresión de consulta equivalente, de modo que deben expresarse como una llamada de método. La sintaxis de método se puede combinar con la sintaxis de consulta de varias maneras. Para más información, vea [Sintaxis de consultas y sintaxis de métodos en LINQ](query-syntax-and-method-syntax-in-linq.md).
- Las expresiones de consulta pueden compilarse en árboles de expresión o en delegados, en función del tipo al que se aplica la consulta. Las consultas <xref:System.Collections.Generic.IEnumerable%601> se compilan en delegados. Las consultas <xref:System.Linq.IQueryable> y <xref:System.Linq.IQueryable%601> se compilan en árboles de expresión. Para más información, vea [Árboles de expresión](../../../expression-trees.md).

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre LINQ, empiece a familiarizarse con algunos conceptos básicos en [Conceptos básicos de las expresiones de consultas](../../../linq/query-expression-basics.md) y, después, lea la documentación de la tecnología de LINQ en la que esté interesado:

- Documentos XML: [LINQ to XML](../../../../standard/linq/linq-xml-overview.md)  
- ADO.NET Entity Framework: [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)
- Colecciones .NET, archivos y cadenas, entre otros: [LINQ to Objects](linq-to-objects.md)

Para comprender mejor los aspectos generales de LINQ, vea [LINQ in C#](../../../linq/linq-in-csharp.md) (LINQ en C#).

Para empezar a trabajar con LINQ en C#, vea el tutorial [Trabajar con LINQ](../../../tutorials/working-with-linq.md).
