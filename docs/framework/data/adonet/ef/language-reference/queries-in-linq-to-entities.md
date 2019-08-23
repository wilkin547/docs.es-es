---
title: Consultas en LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: e6d4b5d1095deb80a866bb0e3821ea10578d7925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933737"
---
# <a name="queries-in-linq-to-entities"></a>Consultas en LINQ to Entities
Una consulta es una expresión que recupera datos de un origen de datos. Las consultas se suelen expresar en un lenguaje de consulta especializado, como SQL para bases de datos relacionales y XQuery para XML. Por lo tanto, los programadores han tenido que aprender un lenguaje de consultas nuevo para cada tipo de origen de datos o formato de datos que consultan. Language-Integrated Query (LINQ) ofrece un modelo coherente y más sencillo para trabajar con los datos de varios formatos y orígenes de datos. En una consulta de LINQ siempre se trabaja con objetos de programación.  
  
 Una operación de consulta de LINQ consta de tres acciones: obtener el origen o los orígenes de datos, crear la consulta y ejecutar la consulta.  
  
 Los orígenes de datos que implementan las interfaces genéricas <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> pueden consultarse a través de LINQ. Las instancias de la <xref:System.Data.Objects.ObjectQuery%601> clase genérica, que implementa la interfaz <xref:System.Linq.IQueryable%601> genérica, actúan como origen de datos para las consultas de LINQ to Entities. La clase <xref:System.Data.Objects.ObjectQuery%601> genérica representa una consulta que devuelve una colección de cero o más objetos con tipo. También puede permitir que el compilador deduzca el tipo de una entidad C# mediante `var` la palabra clave (DIM in Visual Basic).  
  
 En la consulta se especifica exactamente la información que se desea recuperar del origen de datos. Una consulta también puede especificar cómo se debe ordenar, agrupar y conformar esa información antes de que se devuelva. En LINQ, una consulta se almacena en una variable. Si la consulta devuelve una secuencia de valores, la propia variable de la consulta debe ser de un tipo que se pueda consultar. Esta variable de consulta no realiza ninguna acción y no devuelve datos; solamente almacena la información de la consulta. Tras crear una consulta debe ejecutarla para recuperar los datos.  
  
## <a name="query-syntax"></a>Sintaxis de consulta  
 Las consultas de LINQ to Entities se pueden formular en dos sintaxis diferentes: sintaxis de expresiones de consulta y sintaxis de consultas basadas en métodos. La sintaxis de las expresiones de C# consulta es nueva en 3,0 y Visual Basic 9,0, y consta de un conjunto de cláusulas escritas en una sintaxis declarativa similar a TRANSACT-SQL o XQuery. Sin embargo, el Common Language Runtime de .NET Framework (CLR) no puede leer la sintaxis de expresiones de consulta en sí. Por lo tanto, en tiempo de compilación, las expresiones de consulta se traducen a algo que CLR no comprende: las llamadas a métodos. Estos métodos se conocen como *operadores de consulta estándar*. Como programador, tiene la opción de llamarlos directamente utilizando la sintaxis de método en lugar de la sintaxis de consulta. Para obtener más información, vea [Query Syntax and Method Syntax in LINQ](../../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consulta y sintaxis de método en LINQ).  
  
### <a name="query-expression-syntax"></a>Sintaxis de expresiones de consulta  
 Las expresiones de consulta son una sintaxis de consulta declarativa. Esta sintaxis permite a un programador escribir consultas en un lenguaje de alto nivel que tenga un formato similar al de Transact-SQL. Si se utiliza la sintaxis de expresiones de consulta, se pueden realizar incluso operaciones complejas de filtrado, ordenación y agrupamiento en orígenes de datos con código mínimo. Para obtener más información, [consulte operaciones básicas de consulta (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Para obtener ejemplos que muestran cómo utilizar la sintaxis de expresiones de consulta, vea los siguientes temas:  
  
- [Ejemplos de sintaxis de expresiones de consulta: Estando](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: Filtra](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: Pide](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: Operadores de agregado](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: Particiones](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: Operadores de combinación](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: Operadores de elementos](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: Agrupación](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: Navegar por las relaciones](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Sintaxis de consultas basadas en métodos  
 Otra forma de crear consultas LINQ to Entities es mediante el uso de consultas basadas en métodos. La sintaxis de las consultas basadas en métodos es una secuencia de llamadas de método directo a los métodos de operador de LINQ, pasando expresiones lambda como parámetros. Para obtener más información, vea [Expresiones lambda](../../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Para obtener ejemplos que muestran cómo utilizar la sintaxis basada en métodos, vea los siguientes temas:  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Estando](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Filtra](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Pide](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Operadores de agregado](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Particiones](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Version](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Operadores de combinación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Operadores de elementos](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Agrupación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: Navegar por las relaciones](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>Vea también

- [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [Introducción a LINQ en C#](../../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Introducción a LINQ en Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Entity Framework opciones de combinación y consultas compiladas](https://go.microsoft.com/fwlink/?LinkId=199591)
