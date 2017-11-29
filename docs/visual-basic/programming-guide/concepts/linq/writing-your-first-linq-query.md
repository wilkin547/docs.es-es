---
title: Escribir la primera consulta con LINQ (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: "56"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c16bb28189d5525654328da2dc80d868bbe61bf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Escribir la primera consulta con LINQ (Visual Basic)
Una *consulta* es una expresión que recupera datos de un origen de datos. Las consultas se expresan en un lenguaje de consulta dedicado. Con el tiempo, distintos idiomas han ha desarrollado para diferentes tipos de orígenes de datos, por ejemplo, SQL para bases de datos relacionales y XQuery para XML. Esto hace que sea necesario para el desarrollador de aplicaciones aprender un nuevo lenguaje de consulta para cada tipo de origen de datos o formato de datos que se admite.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]simplifica la situación, ya que ofrece un modelo coherente para trabajar con datos de varios formatos y orígenes de datos. En una consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] siempre se trabaja con objetos. Utilice los mismos modelos de codificación básicos para consultar y transformar datos de documentos XML, bases de datos SQL, conjuntos de datos ADO.NET y entidades, las colecciones de .NET Framework y cualquier otro origen o formato para el que un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] proveedor está disponible. Este documento describen las tres fases de la creación y el uso de basic [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consultas.  
  
## <a name="three-stages-of-a-query-operation"></a>Tres etapas de una operación de consulta  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]operaciones de consulta se componen de tres acciones:  
  
1.  Obtener el origen de datos o los orígenes.  
  
2.  Crear la consulta.  
  
3.  Ejecutar la consulta.  
  
 En [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], la ejecución de una consulta es distinta de la creación de la consulta. No recuperar los datos mediante la creación de una consulta. Este punto se analiza con más detalle más adelante en este tema.  
  
 En el ejemplo siguiente se muestra las tres partes de una operación de consulta. El ejemplo usa una matriz de enteros como un origen de datos adecuada para fines de demostración. Sin embargo, los mismos conceptos también se aplican a otros orígenes de datos.  
  
> [!NOTE]
>  En el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que **Option infer** está establecido en **en**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Resultado:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>El origen de datos  
 Dado que el origen de datos en el ejemplo anterior es una matriz, se admite implícitamente la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> interfaz. Es este hecho lo que le permite usar una matriz como un origen de datos para un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta. Los tipos compatibles con <xref:System.Collections.Generic.IEnumerable%601> o una interfaz derivada, como la interfaz genérica <xref:System.Linq.IQueryable%601>, se denominan *tipos consultables*.  
  
 Como un tipo implícitamente consultable, la matriz no requiere modificaciones ni un tratamiento especial para actuar como un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origen de datos. Lo mismo puede decirse de cualquier tipo de colección que admita <xref:System.Collections.Generic.IEnumerable%601>, incluida la interfaz genérica <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>y otras clases de la biblioteca de clases de .NET Framework.  
  
 Si los datos de origen no implementan ya <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] proveedor es necesario para implementar la funcionalidad de la *operadores de consulta estándar* para ese origen de datos. Por ejemplo, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] administra el trabajo de cargar un documento XML en un consultable <xref:System.Xml.Linq.XElement> type, tal como se muestra en el ejemplo siguiente. Para obtener más información acerca de los operadores de consulta estándar, vea [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Con [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], crea primero una asignación relacional de objetos en tiempo de diseño, ya sea manualmente o mediante el [LINQ to SQL Tools en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) en Visual Studio. Después, se escriben las consultas en los objetos y, en tiempo de ejecución, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] controla la comunicación con la base de datos. En el ejemplo siguiente, `customers` representa una tabla específica de la base de datos y <xref:System.Data.Linq.Table%601> admite genérico <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Para obtener más información sobre cómo crear tipos específicos de orígenes de datos, vea la documentación de los distintos proveedores de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. (Para obtener una lista de estos proveedores, vea [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).) La regla básica es simple: un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origen de datos es cualquier objeto que admita la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> interfaz o una interfaz que hereda de ella.  
  
> [!NOTE]
>  Tipos como <xref:System.Collections.ArrayList> que admiten no genérica <xref:System.Collections.IEnumerable> interfaz también se puede usar como [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] orígenes de datos. Para obtener un ejemplo que utiliza un <xref:System.Collections.ArrayList>, consulte [Cómo: consultar un objeto ArrayList con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>La consulta  
 En la consulta, especifique la información que van a recuperar desde el origen de datos u orígenes. También tiene la opción de especificar cómo debe ordenar, agrupar o estructurada antes de que se devuelva esa información. Para habilitar la creación de consultas, Visual Basic incorpora nueva sintaxis de consulta en el lenguaje.  
  
 Cuando se ejecuta, la consulta en el ejemplo siguiente devuelve todos los números pares de una matriz de enteros, `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 La expresión de consulta contiene tres cláusulas: `From`, `Where`, y `Select`. La función específica y el propósito de cada cláusula de expresión de consulta se describe en [operaciones básicas de consulta (Visual Basic)](basic-query-operations.md). Para obtener más información, consulte [consultas](../../../../visual-basic/language-reference/queries/queries.md). Tenga en cuenta que en [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], una definición de consulta a menudo se almacena en una variable y ejecutarla más tarde. La consulta variable, como `evensQuery` en el ejemplo anterior, debe ser un tipo consultable. El tipo de `evensQuery` es `IEnumerable(Of Integer)`, asignado por el compilador utiliza la inferencia de tipo local.  
  
 Es importante recordar que la propia variable de consulta no realiza ninguna acción y no devuelve ningún dato. Solo almacena la definición de consulta. En el ejemplo anterior, es el `For Each` bucle que se ejecuta la consulta.  
  
## <a name="query-execution"></a>Ejecución de la consulta  
 Ejecución de la consulta es independiente de la creación de consultas. Creación de consulta define la consulta, pero la ejecución se desencadena mediante un mecanismo diferente. Se puede ejecutar una consulta tan pronto como se define (*ejecución inmediata*), o se puede almacenar la definición y la consulta se puede ejecutar más adelante (*ejecución diferida*).  
  
### <a name="deferred-execution"></a>Ejecución aplazada  
 Una típica [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta es similar a la mostrada en el ejemplo anterior, en el que `evensQuery` está definido. Se crea la consulta pero no la ejecuta inmediatamente. En su lugar, la definición de consulta se almacena en la variable de consulta `evensQuery`. Ejecute la consulta más adelante, normalmente mediante un `For Each` bucles for, que devuelve una secuencia de valores, o aplicando un operador de consulta estándar, como `Count` o `Max`. Este proceso se conoce como *ejecución diferida*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Para una secuencia de valores, tener acceso a los datos recuperados mediante la variable de iteración en la `For Each` bucle (`number` en el ejemplo anterior). Dado que la variable de consulta, `evensQuery`, contiene la definición de consulta en lugar de los resultados de la consulta, puede ejecutar una consulta con tanta frecuencia como desee mediante la variable de consulta más de una vez. Por ejemplo, podría tener una base de datos en la aplicación que se está actualizando continuamente por una aplicación independiente. Después de haber creado una consulta que recupera datos de esa base de datos, puede usar un `For Each` bucle para ejecutar la consulta de forma repetida, recuperar los datos más recientes cada vez.  
  
 En el ejemplo siguiente se muestra cómo la ejecución aplazada funciona. Después de `evensQuery2` se define y se ejecuta con una `For Each` de bucle, como en los ejemplos anteriores, algunos elementos del origen de datos `numbers` se cambian. A continuación, un segundo `For Each` se ejecuta un bucle `evensQuery2` nuevo. Los resultados son diferentes la segunda vez, porque el `For Each` bucle ejecuta la consulta de nuevo, con los nuevos valores en `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Resultado:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Ejecución inmediata  
 En la ejecución aplazada de consultas, la definición de consulta se almacena en una variable de consulta para su ejecución posterior. En la ejecución inmediata, la consulta se ejecuta en el momento de su definición. La ejecución se desencadena cuando se aplica a un método que requiere acceso a los elementos individuales del resultado de la consulta. A menudo la ejecución inmediata se fuerza mediante uno de los operadores de consulta estándar que devuelven valores únicos. Algunos ejemplos son `Count`, `Max`, `Average`, y `First`. Estos operadores de consulta estándar ejecutan la consulta en cuanto se aplican para calcular y devolver un resultado singleton. Para obtener más información acerca de los operadores de consulta estándar que devuelven valores únicos, vea [operaciones de agregación](aggregation-operations.md), [las operaciones de elementos](element-operations.md), y [operaciones cuantificadoras](quantifier-operations.md).  
  
 La consulta siguiente devuelve un recuento de los números pares en una matriz de enteros. No se guarda la definición de consulta, y `numEvens` es una sencilla `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Puede conseguir el mismo resultado mediante la `Aggregate` método.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 También puede forzar la ejecución de una consulta mediante una llamada a la `ToList` o `ToArray` método en una consulta (inmediata) o variable de consulta (diferida), como se muestra en el código siguiente.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 En los ejemplos anteriores, `evensQuery3` es una consulta de variable, pero `evensList` es una lista y `evensArray` es una matriz.  
  
 Usar `ToList` o `ToArray` para forzar inmediatamente la ejecución es especialmente útil en escenarios en los que desea ejecutar la consulta inmediatamente y almacenar en caché los resultados en un objeto de colección único. Para obtener más información acerca de estos métodos, consulte [convertir tipos de datos](converting-data-types.md).  
  
 También puede hacer que una consulta se puede ejecutar mediante el uso de un `IEnumerable` método, como el <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> método.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](getting-started-with-linq.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)
