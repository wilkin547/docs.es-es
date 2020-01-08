---
title: Consultas en LINQ to DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c1a78fa8-9f0c-40bc-a372-5575a48708fe
ms.openlocfilehash: 092dbb5227e5f9e0ae2a62656a300d2367bcf16b
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634799"
---
# <a name="queries-in-linq-to-dataset"></a>Consultas en LINQ to DataSet
Una consulta es una expresión que recupera datos de un origen de datos. Las consultas se suelen expresar en un lenguaje de consulta especializado, como SQL para bases de datos relacionales y XQuery para XML. Por lo tanto, los programadores han tenido que aprender un lenguaje de consultas nuevo para cada tipo de origen de datos o formato de datos que consultan. Language-Integrated Query (LINQ) ofrece un modelo coherente y más sencillo para trabajar con los datos de varios formatos y orígenes de datos. En una consulta de LINQ siempre se trabaja con objetos de programación.  
  
 Una operación de consulta de LINQ consta de tres acciones: obtener el origen o los orígenes de datos, crear la consulta y ejecutar la consulta.  
  
 Los orígenes de datos que implementan la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> se pueden consultar a través de LINQ. La llamada a <xref:System.Data.DataTableExtensions.AsEnumerable%2A> en un <xref:System.Data.DataTable> devuelve un objeto que implementa la interfaz genérica de <xref:System.Collections.Generic.IEnumerable%601>, que actúa como origen de datos para las consultas de LINQ to DataSet.  
  
 En la consulta se especifica exactamente la información que se desea recuperar del origen de datos. Una consulta también puede especificar cómo se debe ordenar, agrupar y conformar esa información antes de que se devuelva. En LINQ, una consulta se almacena en una variable. Si la consulta está diseñada para devolver una secuencia de valores, la variable misma de la consulta debe ser de tipo enumerable. Esta variable de consulta no realiza ninguna acción y no devuelve datos; solamente almacena la información de la consulta. Tras crear una consulta debe ejecutarla para recuperar los datos.  
  
 En una consulta que devuelve una secuencia de valores, la variable de consulta por sí misma nunca conserva los resultados de la consulta y solo almacena los comandos de la misma. La ejecución de la consulta se aplaza hasta que la variable de consulta se recorre en iteración en un bucle `foreach` o `For Each`. Esto se denomina *ejecución aplazada*; es decir, la ejecución de la consulta se produce una vez después de la construcción de la consulta. Esto significa que se puede ejecutar una consulta con la frecuencia que se desee. Esto es útil cuando, por ejemplo, se tiene una base de datos que otras aplicaciones están actualizando. En su aplicación puede crear una consulta para recuperar la información más reciente y ejecutar de forma repetida la consulta, devolviendo cada vez la información actualizada.  
  
 A diferencia de las consultas en diferido, que devuelven una secuencia de valores, las consultas que devuelven un valor singleton se ejecutan inmediatamente. Algunos ejemplos de consultas singleton son <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Average%2A> y <xref:System.Linq.Enumerable.First%2A>. Se ejecutan inmediatamente porque se necesitan los resultados de la consulta para calcular el resultado singleton. Por ejemplo, para buscar la media de los resultados de consultas, debe ejecutarse la consulta para que la función de cálculo de media tenga datos de entrada con los que trabajar. También puede usar los métodos <xref:System.Linq.Enumerable.ToList%2A> o <xref:System.Linq.Enumerable.ToArray%2A> en una consulta para forzar la ejecución inmediata de una consulta que no crea un valor singleton. Esas técnicas para forzar la ejecución inmediata pueden ser útiles si desea almacenar en caché los resultados de una consulta.
  
## <a name="queries"></a>Consultas  
 LINQ to DataSet consultas se pueden formular en dos sintaxis diferentes: sintaxis de expresiones de consulta y sintaxis de consulta basada en métodos.  
  
### <a name="query-expression-syntax"></a>Sintaxis de la expresión de consulta de  
 Las expresiones de consulta son una sintaxis de consulta declarativa. Esta sintaxis permite a un desarrollador escribir consultas en C# o Visual Basic en un formato similar a SQL. Si se utiliza la sintaxis de expresiones de consulta, se pueden realizar incluso operaciones complejas de filtrado, ordenación y agrupamiento en orígenes de datos con código mínimo. Para obtener más información, vea [expresiones de consulta LINQ](../../../csharp/linq/index.md#query-expression-overview) y [operaciones básicas de consulta (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).
  
 El Common Language Runtime de .NET Framework (CLR) no puede leer la sintaxis de expresiones de consulta en sí. Por lo tanto, en tiempo de compilación, las expresiones de consulta se traducen a algo que CLR no comprende: las llamadas a métodos. Estos métodos se conocen como operadores de *consulta estándar*. Como programador, tiene la opción de llamarlos directamente utilizando la sintaxis de método en lugar de la sintaxis de consulta. Para obtener más información, vea [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consulta y sintaxis de método en LINQ). Para obtener más información acerca de los operadores de consulta estándar, vea [información general sobre operadores de consulta estándar](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 El siguiente ejemplo usa <xref:System.Linq.Enumerable.Select%2A> para devolver todas las filas de la tabla `Product` y mostrar los nombres de producto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="method-based-query-syntax"></a>Sintaxis de consultas basadas en métodos  
 La otra forma de formular consultas LINQ to DataSet es mediante el uso de consultas basadas en métodos. La sintaxis de las consultas basadas en métodos es una secuencia de llamadas de método directo a los métodos de operador de LINQ, pasando expresiones lambda como parámetros. Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Este ejemplo usa <xref:System.Linq.Enumerable.Select%2A> para devolver todas las filas de `Product` y mostrar los nombres de producto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="composing-queries"></a>Crear consultas  
 Tal y como se ha mencionado anteriormente en este tema, la variable de consulta solo almacena los comandos de la consulta cuando ésta se diseña para devolver una secuencia de valores. Si la consulta no contiene un método que cause una ejecución inmediata, la ejecución real de la consulta se aplaza hasta que la variable de consulta se recorra en iteración en un bucle `foreach` o `For Each`. La ejecución aplazada permite combinar varias consultas o ampliar una consulta. Cuando se amplía una consulta, se modifica para incluir las nuevas operaciones. La ejecución eventual reflejará los cambios. En el siguiente ejemplo, la primera consulta devuelve todos los productos. La segunda consulta amplía la primera usando `Where` para devolver todos los productos del tamaño "L":  
  
 [!code-csharp[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#composing)]
 [!code-vb[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#composing)]  
  
 Una vez que se ha ejecutado una consulta, no se pueden crear consultas adicionales y todas las consultas posteriores utilizarán los operadores de LINQ en memoria. La ejecución de la consulta se producirá al recorrer en iteración la variable de consulta en una instrucción `foreach` o `For Each`, o mediante una llamada a uno de los operadores de conversión de LINQ que causan la ejecución inmediata. Entre estos operadores se incluyen los siguientes: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> y <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
 En el siguiente ejemplo, la primera consulta devuelve todos los productos ordenados por el precio de la lista. El método <xref:System.Linq.Enumerable.ToArray%2A> se usa para forzar la ejecución inmediata de la consulta:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray2)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray2)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación](programming-guide-linq-to-dataset.md)
- [Consulta de conjuntos de datos](querying-datasets-linq-to-dataset.md)
- [Introducción a LINQ en C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
