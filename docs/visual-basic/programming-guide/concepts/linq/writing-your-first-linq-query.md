---
title: Escritura de la primera consulta con LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 9d85f9c0390a659e59e372ad949cffdd17715189
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413263"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Escribir la primera consulta con LINQ (Visual Basic)
Una *consulta* es una expresión que recupera datos de un origen de datos. Las consultas se expresan en un lenguaje de consulta dedicado. Con el tiempo, se han desarrollado distintos lenguajes para distintos tipos de orígenes de datos, por ejemplo, SQL para bases de datos relacionales y XQuery para XML. Esto hace que sea necesario que el desarrollador de la aplicación Aprenda un nuevo lenguaje de consulta para cada tipo de origen de datos o formato de datos que se admita.  
  
 Language-Integrated Query (LINQ) simplifica la situación al ofrecer un modelo coherente para trabajar con datos en varios tipos de orígenes de datos y formatos. En una consulta LINQ siempre se trabaja con objetos. Puede usar los mismos patrones de codificación básicos para consultar y transformar datos en documentos XML, bases de datos SQL, conjuntos de datos y entidades de ADO.NET, colecciones de .NET Framework y cualquier otro origen o formato para el que haya disponible un proveedor LINQ. En este documento se describen las tres fases de la creación y el uso de consultas LINQ básicas.  
  
## <a name="three-stages-of-a-query-operation"></a>Tres fases de una operación de consulta  
 Las operaciones de consulta LINQ constan de tres acciones:  
  
1. Obtener el origen o los orígenes de datos.  
  
2. Crear la consulta.  
  
3. Ejecutar la consulta.  
  
 En LINQ, la ejecución de una consulta es distinta de la creación de la consulta. No se recuperan datos mediante la creación de una consulta. Este punto se analiza con más detalle más adelante en este tema.  
  
 En el ejemplo siguiente se muestran las tres partes de una operación de consulta. En el ejemplo se usa una matriz de enteros como un origen de datos adecuado para fines de demostración. Sin embargo, los mismos conceptos también se aplican a otros orígenes de datos.  
  
> [!NOTE]
> En la [Página compilar, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que la **opción Infer** está establecida en **on**.  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 Salida:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>El origen de datos  
 Dado que el origen de datos del ejemplo anterior es una matriz, admite implícitamente la <xref:System.Collections.Generic.IEnumerable%601> interfaz genérica. Es este hecho que le permite usar una matriz como origen de datos para una consulta LINQ. Los tipos compatibles con <xref:System.Collections.Generic.IEnumerable%601> o una interfaz derivada, como la interfaz genérica <xref:System.Linq.IQueryable%601>, se denominan *tipos consultables*.  
  
 Como un tipo que se pueda consultar implícitamente, la matriz no requiere ninguna modificación ni tratamiento especial para servir como origen de datos LINQ. Lo mismo se aplica a cualquier tipo de colección que admita <xref:System.Collections.Generic.IEnumerable%601> , incluidas las <xref:System.Collections.Generic.List%601> clases genéricas, <xref:System.Collections.Generic.Dictionary%602> y otras de la biblioteca de clases .NET Framework.  
  
 Si los datos de origen no implementan ya <xref:System.Collections.Generic.IEnumerable%601> , se necesita un proveedor LINQ para implementar la funcionalidad de los *operadores de consulta estándar* para ese origen de datos. Por ejemplo, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] controla el trabajo de carga de un documento XML en un tipo consultable <xref:System.Xml.Linq.XElement> , tal como se muestra en el ejemplo siguiente. Para obtener más información acerca de los operadores de consulta estándar, consulte [Introducción a los operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#2)]  
  
 Con [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] , primero se crea una asignación relacional de objetos en tiempo de diseño, ya sea manualmente o mediante el [LINQ to SQL herramientas de Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) en Visual Studio. Después, se escriben las consultas en los objetos y, en tiempo de ejecución, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] controla la comunicación con la base de datos. En el ejemplo siguiente, `customers` representa una tabla específica en la base de datos y <xref:System.Data.Linq.Table%601> admite Generic <xref:System.Linq.IQueryable%601> .  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Para obtener más información sobre cómo crear tipos específicos de orígenes de datos, consulte la documentación de los distintos proveedores de LINQ. (Para obtener una lista de estos proveedores, consulte [LINQ (Language-Integrated Query)](index.md)). La regla básica es sencilla: un origen de datos LINQ es cualquier objeto que admita la <xref:System.Collections.Generic.IEnumerable%601> interfaz genérica o una interfaz que herede de ella.  
  
> [!NOTE]
> Los tipos como <xref:System.Collections.ArrayList> que admiten la interfaz no genérica <xref:System.Collections.IEnumerable> también se pueden usar como orígenes de datos de Linq. Para obtener un ejemplo en <xref:System.Collections.ArrayList> el que se usa, vea [Cómo: consultar una ARRAYLIST con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>Consulta  
 En la consulta, se especifica la información que se desea recuperar del origen de datos o de los orígenes. También tiene la opción de especificar cómo se debe ordenar, agrupar o estructurar esa información antes de que se devuelva. Para habilitar la creación de consultas, Visual Basic ha incorporado una nueva sintaxis de consulta en el lenguaje.  
  
 Cuando se ejecuta, la consulta del ejemplo siguiente devuelve todos los números pares de una matriz de enteros, `numbers` .  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 La expresión de consulta contiene tres cláusulas: `From` , `Where` y `Select` . La función y el propósito específicos de cada cláusula de expresión de consulta se describen en [operaciones básicas de consulta (Visual Basic)](basic-query-operations.md). Para obtener más información, vea [consultas](../../../language-reference/queries/index.md). Tenga en cuenta que en LINQ, una definición de consulta a menudo se almacena en una variable y se ejecuta más adelante. La variable de consulta, como `evensQuery` en el ejemplo anterior, debe ser un tipo consultable. El tipo de `evensQuery` es `IEnumerable(Of Integer)` , asignado por el compilador mediante la inferencia de tipo de local.  
  
 Es importante recordar que la propia variable de consulta no realiza ninguna acción y no devuelve ningún dato. Solo almacena la definición de la consulta. En el ejemplo anterior, es el `For Each` bucle el que ejecuta la consulta.  
  
## <a name="query-execution"></a>Ejecución de la consulta  
 La ejecución de consultas es independiente de la creación de consultas. La creación de consultas define la consulta, pero la ejecución se desencadena mediante un mecanismo diferente. Una consulta se puede ejecutar en cuanto se define (*ejecución inmediata*) o se puede almacenar la definición y la consulta se puede ejecutar más adelante (*ejecución aplazada*).  
  
### <a name="deferred-execution"></a>Ejecución aplazada  
 Una consulta LINQ típica es similar A la del ejemplo anterior, en la que `evensQuery` se define. Crea la consulta, pero no la ejecuta inmediatamente. En su lugar, la definición de consulta se almacena en la variable de consulta `evensQuery` . La consulta se ejecuta más adelante, normalmente mediante un `For Each` bucle, que devuelve una secuencia de valores o aplicando un operador de consulta estándar, como `Count` o `Max` . Este proceso se conoce como *ejecución aplazada*.  
  
 [!code-vb[VbLINQFirstQuery#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#7)]  
  
 En el caso de una secuencia de valores, se obtiene acceso a los datos recuperados mediante la variable de iteración del `For Each` bucle ( `number` en el ejemplo anterior). Dado que la variable de consulta, `evensQuery` , contiene la definición de la consulta en lugar de los resultados de la consulta, puede ejecutar una consulta tantas veces como desee utilizando la variable de consulta más de una vez. Por ejemplo, podría tener una base de datos en la aplicación que se está actualizando continuamente mediante una aplicación independiente. Después de crear una consulta que recupere datos de esa base de datos, puede usar un `For Each` bucle para ejecutar la consulta repetidamente y recuperar los datos más recientes cada vez.  
  
 En el ejemplo siguiente se muestra cómo funciona la ejecución aplazada. Una vez `evensQuery2` que se define y se ejecuta con un `For Each` bucle, como en los ejemplos anteriores, algunos elementos del origen de datos `numbers` cambian. A continuación, `For Each` se ejecuta de nuevo un segundo bucle `evensQuery2` . Los resultados son diferentes por segunda vez, ya que el `For Each` bucle vuelve a ejecutar la consulta con los nuevos valores de `numbers` .  
  
 [!code-vb[VbLINQFirstQuery#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#3)]  
  
 Salida:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Ejecución inmediata  
 En la ejecución diferida de consultas, la definición de consulta se almacena en una variable de consulta para su ejecución posterior. En la ejecución inmediata, la consulta se ejecuta en el momento de su definición. La ejecución se desencadena cuando se aplica un método que requiere acceso a elementos individuales del resultado de la consulta. A menudo, la ejecución inmediata se fuerza mediante el uso de uno de los operadores de consulta estándar que devuelven valores únicos. Algunos ejemplos son `Count` ,, `Max` `Average` y `First` . Estos operadores de consulta estándar ejecutan la consulta tan pronto como se aplican para calcular y devolver un resultado singleton. Para obtener más información sobre los operadores de consulta estándar que devuelven valores únicos, vea operaciones de [agregación](aggregation-operations.md), [operaciones de elementos](element-operations.md)y [operaciones de cuantificador](quantifier-operations.md).  
  
 La consulta siguiente devuelve un recuento de los números pares en una matriz de enteros. La definición de consulta no se guarda y `numEvens` es una sencilla `Integer` .  
  
 [!code-vb[VbLINQFirstQuery#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#4)]  
  
 Puede lograr el mismo resultado mediante el `Aggregate` método.  
  
 [!code-vb[VbLINQFirstQuery#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#5)]  
  
 También puede forzar la ejecución de una consulta mediante una llamada al `ToList` `ToArray` método o en una consulta (inmediato) o una variable de consulta (aplazada), como se muestra en el código siguiente.  
  
 [!code-vb[VbLINQFirstQuery#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#6)]  
  
 En los ejemplos anteriores, `evensQuery3` es una variable de consulta, pero `evensList` es una lista y `evensArray` es una matriz.  
  
 Usar `ToList` o `ToArray` para forzar la ejecución inmediata es especialmente útil en escenarios en los que desea ejecutar la consulta inmediatamente y almacenar en caché los resultados en un objeto de colección único. Para obtener más información sobre estos métodos, vea [convertir tipos de datos](converting-data-types.md).  
  
 También puede hacer que se ejecute una consulta mediante un `IEnumerable` método como el <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> método.  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](getting-started-with-linq.md)
- [Inferencia de tipo de variable local](../../language-features/variables/local-type-inference.md)
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)
- [Introducción a LINQ en Visual Basic](../../language-features/linq/introduction-to-linq.md)
- [LINQ](../../language-features/linq/index.md)
- [Consultas](../../../language-reference/queries/index.md)
