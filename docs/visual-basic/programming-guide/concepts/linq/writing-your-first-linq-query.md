---
title: Escribir la primera consulta con LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 4c04c00c5392d8ba363346b06c806ec79041c439
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46326389"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Escribir la primera consulta con LINQ (Visual Basic)
Una *consulta* es una expresión que recupera datos de un origen de datos. Las consultas se expresan en un lenguaje de consulta dedicado. Con el tiempo, distintos idiomas se han desarrollado para diferentes tipos de orígenes de datos, por ejemplo, SQL para bases de datos relacionales y XQuery para XML. Esto hace que sea necesario para el desarrollador de aplicaciones obtener información sobre un nuevo lenguaje de consulta para cada tipo de origen de datos o formato de datos que se admite.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] simplifica la situación al ofrecer un modelo coherente para trabajar con datos de varios formatos y orígenes de datos. En una consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] siempre se trabaja con objetos. Utilice los mismos modelos de codificación básicos para consultar y transformar datos de documentos XML, bases de datos SQL, datasets de ADO.NET y entidades, las colecciones de .NET Framework y cualquier otro origen o formato para el que un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] proveedor está disponible. Este documento describe las tres fases de la creación y uso de basic [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consultas.  
  
## <a name="three-stages-of-a-query-operation"></a>Tres fases de una operación de consulta  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] las operaciones de consulta se componen de tres acciones:  
  
1.  Obtener el origen de datos o los orígenes.  
  
2.  Crear la consulta.  
  
3.  Ejecutar la consulta.  
  
 En [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], la ejecución de una consulta es distinta de la creación de la consulta. No recuperar los datos mediante la creación de una consulta. Este punto se analiza con más detalle más adelante en este tema.  
  
 El ejemplo siguiente muestra las tres partes de una operación de consulta. El ejemplo utiliza una matriz de enteros como un origen de datos adecuada para fines de demostración. Sin embargo, los mismos conceptos se aplican también a otros orígenes de datos.  
  
> [!NOTE]
>  En el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que **Option infer** está establecido en **en**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Resultado:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>El origen de datos  
 Dado que el origen de datos en el ejemplo anterior es una matriz, admite implícitamente el tipo genérico <xref:System.Collections.Generic.IEnumerable%601> interfaz. Es este hecho que le permite usar una matriz como origen de datos para un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta. Los tipos compatibles con <xref:System.Collections.Generic.IEnumerable%601> o una interfaz derivada, como la interfaz genérica <xref:System.Linq.IQueryable%601>, se denominan *tipos consultables*.  
  
 Como un tipo consultable implícitamente, la matriz requiere ninguna modificación ni ningún tratamiento especial para actuar como un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origen de datos. Lo mismo puede decirse de cualquier tipo de colección que admita <xref:System.Collections.Generic.IEnumerable%601>, incluido el genérico <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>y otras clases en la biblioteca de clases de .NET Framework.  
  
 Si los datos de origen ya no implementan <xref:System.Collections.Generic.IEnumerable%601>, un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] proveedor es necesario para implementar la funcionalidad de la *operadores de consulta estándar* para ese origen de datos. Por ejemplo, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] controla el trabajo de cargar un documento XML en un consultable <xref:System.Xml.Linq.XElement> escribe, tal como se muestra en el ejemplo siguiente. Para obtener más información acerca de los operadores de consulta estándar, consulte [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Con [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], primero se crea una asignación relacional de objetos en tiempo de diseño, ya sea manualmente o mediante el [LINQ to SQL Tools en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) en Visual Studio. Después, se escriben las consultas en los objetos y, en tiempo de ejecución, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] controla la comunicación con la base de datos. En el ejemplo siguiente, `customers` representa una tabla específica en la base de datos y <xref:System.Data.Linq.Table%601> admite genérico <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Para obtener más información sobre cómo crear tipos específicos de orígenes de datos, vea la documentación de los distintos proveedores de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. (Para obtener una lista de estos proveedores, consulte [LINQ (Language-Integrated Query)](../../../../visual-basic/programming-guide/concepts/linq/index.md).) La regla básica es simple: un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origen de datos es cualquier objeto que admite el tipo genérico <xref:System.Collections.Generic.IEnumerable%601> interfaz o una interfaz que hereda de ella.  
  
> [!NOTE]
>  Los tipos, como <xref:System.Collections.ArrayList> que admiten la no genérica <xref:System.Collections.IEnumerable> interfaz también puede usarse como [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] orígenes de datos. Para obtener un ejemplo que usa un <xref:System.Collections.ArrayList>, consulte [Cómo: consultar un objeto ArrayList con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>La consulta  
 En la consulta, especifique qué desea recuperar desde el origen de datos u orígenes de información. También tiene la opción de especificar cómo debe ordenan, agrupan o estructurada antes de que se devuelva esa información. Para habilitar la creación de consultas, Visual Basic incorpora la nueva sintaxis de consulta en el lenguaje.  
  
 Cuando se ejecuta la consulta en el ejemplo siguiente devuelve todos los números de una matriz de enteros, `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 La expresión de consulta contiene tres cláusulas: `From`, `Where`, y `Select`. La función específica y el propósito de cada cláusula de expresión de consulta se analiza en [operaciones básicas de consulta (Visual Basic)](basic-query-operations.md). Para obtener más información, consulte [consultas](../../../../visual-basic/language-reference/queries/index.md). Tenga en cuenta que en [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], una definición de consulta a menudo se almacena en una variable y ejecutará más adelante. La consulta variable, como `evensQuery` en el ejemplo anterior, debe ser un tipo consultable. El tipo de `evensQuery` es `IEnumerable(Of Integer)`, asignado por el compilador utiliza la inferencia de tipo local.  
  
 Es importante recordar que la variable de consulta no realiza ninguna acción y no devuelve ningún dato. Solo almacena la definición de consulta. En el ejemplo anterior, es el `For Each` bucle que se ejecuta la consulta.  
  
## <a name="query-execution"></a>Ejecución de la consulta  
 Ejecución de la consulta es independiente de la creación de consultas. Creación de consulta define la consulta, pero la ejecución la desencadena un mecanismo diferente. Se puede ejecutar una consulta tan pronto como se define (*ejecución inmediata*), o se puede almacenar la definición y la consulta se puede ejecutar más adelante (*ejecución aplazada*).  
  
### <a name="deferred-execution"></a>Ejecución aplazada  
 Una típica [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta es similar a la mostrada en el ejemplo anterior, en el que `evensQuery` está definido. Crea la consulta pero no la ejecuta inmediatamente. En su lugar, la definición de consulta se almacena en la variable de consulta `evensQuery`. Ejecutar la consulta más adelante, normalmente mediante un `For Each` bucle, que devuelve una secuencia de valores, o bien aplicando un operador de consulta estándar, tales como `Count` o `Max`. Este proceso se conoce como *ejecución aplazada*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Para una secuencia de valores, tener acceso a los datos recuperados mediante el uso de la variable de iteración en la `For Each` bucle (`number` en el ejemplo anterior). Dado que la variable de consulta, `evensQuery`, contiene la definición de consulta en lugar de los resultados de consulta, puede ejecutar una consulta con tanta frecuencia como desee con la variable de consulta más de una vez. Por ejemplo, podría tener una base de datos en la aplicación que se está actualizando continuamente por una aplicación independiente. Después de haber creado una consulta que recupera datos de esa base de datos, puede usar un `For Each` bucle para ejecutar la consulta de forma repetida, recuperar los datos más recientes cada vez.  
  
 En el ejemplo siguiente se muestra cómo la ejecución aplazada funciona. Después de `evensQuery2` se definen y se ejecuta con un `For Each` bucle, como se muestra en los ejemplos anteriores, algunos elementos del origen de datos `numbers` se cambian. A continuación, un segundo `For Each` se ejecuta un bucle `evensQuery2` nuevo. Los resultados son diferentes la segunda vez, porque el `For Each` bucle ejecuta la consulta de nuevo, con los nuevos valores en `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Resultado:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Ejecución inmediata  
 En la ejecución aplazada de consultas, la definición de consulta se almacena en una variable de consulta para su ejecución posterior. En la ejecución inmediata, la consulta se ejecuta en el momento de su definición. Se desencadena la ejecución cuando se aplica a un método que requiere acceso a los elementos individuales del resultado de la consulta. Se fuerza la ejecución inmediata mediante uno de los operadores de consulta estándar que devuelven valores únicos. Algunos ejemplos son `Count`, `Max`, `Average`, y `First`. Estos operadores de consulta estándar ejecutan la consulta, en cuanto se aplican para calcular y devolver un resultado singleton. Para obtener más información acerca de los operadores de consulta estándar que devuelven valores únicos, vea [operaciones de agregación](aggregation-operations.md), [operaciones de elementos](element-operations.md), y [operaciones cuantificadoras](quantifier-operations.md).  
  
 La consulta siguiente devuelve un recuento de los números pares en una matriz de enteros. No se guarda la definición de consulta, y `numEvens` es una sencilla `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Puede lograr el mismo resultado utilizando la `Aggregate` método.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 También puede forzar la ejecución de una consulta mediante una llamada a la `ToList` o `ToArray` método en una consulta (inmediato) o una variable de consulta (diferida), tal como se muestra en el código siguiente.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 En los ejemplos anteriores, `evensQuery3` es una consulta de variable, pero `evensList` es una lista y `evensArray` es una matriz.  
  
 Uso de `ToList` o `ToArray` para forzar inmediatamente la ejecución es especialmente útil en escenarios en los que desea ejecutar la consulta inmediatamente y almacenar en caché los resultados en un objeto de colección. Para obtener más información acerca de estos métodos, consulte [convertir tipos de datos](converting-data-types.md).  
  
 También puede hacer que una consulta que se ejecuta mediante el uso de un `IEnumerable` método como el <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> método.  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](getting-started-with-linq.md)  
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)  
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
