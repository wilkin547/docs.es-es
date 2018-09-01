---
title: Consultas en LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: b6dc38951107b0d3833e1060c23962a43936bf4d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385512"
---
# <a name="queries-in-linq-to-entities"></a>Consultas en LINQ to Entities
Una consulta es una expresión que recupera datos de un origen de datos. Las consultas se suelen expresar en un lenguaje de consulta especializado, como SQL para bases de datos relacionales y XQuery para XML. Por lo tanto, los programadores han tenido que aprender un lenguaje de consultas nuevo para cada tipo de origen de datos o formato de datos que consultan. Language-Integrated Query (LINQ) ofrece un modelo coherente y más sencillo para trabajar con los datos de varios formatos y orígenes de datos. En una consulta de LINQ siempre se trabaja con objetos de programación.  
  
 Una operación de consulta de LINQ consta de tres acciones: obtener el origen o los orígenes de datos, crear la consulta y ejecutar la consulta.  
  
 Los orígenes de datos que implementan las interfaces genéricas <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> pueden consultarse a través de LINQ. Las instancias de la clase genérica <xref:System.Data.Objects.ObjectQuery%601> (clase), que implementa el modelo genérico <xref:System.Linq.IQueryable%601> interfaz, actúan como origen de datos para [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] consultas. La clase <xref:System.Data.Objects.ObjectQuery%601> genérica representa una consulta que devuelve una colección de cero o más objetos con tipo. También puede hacer que el compilador infiera el tipo de una entidad con la palabra clave de C# `var` (Dim en Visual Basic).  
  
 En la consulta se especifica exactamente la información que se desea recuperar del origen de datos. Una consulta también puede especificar cómo se debe ordenar, agrupar y conformar esa información antes de que se devuelva. En LINQ, una consulta se almacena en una variable. Si la consulta devuelve una secuencia de valores, la propia variable de la consulta debe ser de un tipo que se pueda consultar. Esta variable de consulta no realiza ninguna acción y no devuelve datos; solamente almacena la información de la consulta. Tras crear una consulta debe ejecutarla para recuperar los datos.  
  
## <a name="query-syntax"></a>Sintaxis de consulta  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] las consultas se pueden formular en dos sintaxis diferentes: sintaxis de expresiones y la sintaxis de consulta basada en métodos de consulta. Sintaxis de expresiones de consulta es nueva en C# 3.0 y Visual Basic 9.0, y consta de un conjunto de cláusulas escritas en una sintaxis declarativa similar a Transact-SQL o XQuery. No obstante, Common Language Runtime (CLR) de [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] no puede leer la sintaxis de expresiones de consulta en sí. Por lo tanto, en tiempo de compilación, las expresiones de consulta se traducen a algo que CLR no comprende: las llamadas a métodos. Estos métodos se conocen como el *operadores de consulta estándar*. Como programador, tiene la opción de llamarlos directamente utilizando la sintaxis de método en lugar de la sintaxis de consulta. Para obtener más información, vea [Query Syntax and Method Syntax in LINQ](~/docs/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consulta y sintaxis de método en LINQ).  
  
### <a name="query-expression-syntax"></a>Sintaxis de expresiones de consulta  
 Las expresiones de consulta son una sintaxis de consulta declarativa. Esta sintaxis permite a un programador escribir consultas en un lenguaje de alto nivel que tenga un formato similar al de Transact-SQL. Si se utiliza la sintaxis de expresiones de consulta, se pueden realizar incluso operaciones complejas de filtrado, ordenación y agrupamiento en orígenes de datos con código mínimo. Para obtener más información, [operaciones básicas de consulta (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Para obtener ejemplos que muestran cómo utilizar la sintaxis de expresiones de consulta, vea los siguientes temas:  
  
-   [Ejemplos de sintaxis de expresiones de consulta: proyección](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: filtrado](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: ordenación](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: operadores de agregado](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: particionamiento](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: operadores de combinación](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: operadores de elementos](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: agrupación](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
-   [Ejemplos de sintaxis de expresión de consulta: navegar por relaciones](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Sintaxis de consultas basadas en métodos  
 Otra forma de formular consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] es usar las consultas basadas en métodos. La sintaxis de consulta basada en métodos es una secuencia de llamadas directas a métodos de operador de LINQ, pasando expresiones lambda como parámetros. Para obtener más información, vea [Expresiones lambda](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Para obtener ejemplos que muestran cómo utilizar la sintaxis basada en métodos, vea los siguientes temas:  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: proyección](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: filtrado](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: ordenación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: operadores de agregación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: partición](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: conversión](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: operadores de combinación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: operadores de elementos](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: agrupación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
-   [Ejemplos de sintaxis de consultas basadas en métodos: navegar por relaciones](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>Vea también  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)  
 [Introducción a LINQ en C#](~/docs/csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Introducción a LINQ en Visual Basic](~/docs/visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Opciones de combinación de Entity Framework y consultas compiladas](https://go.microsoft.com/fwlink/?LinkId=199591)
