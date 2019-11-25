---
title: Introducción a LINQ
ms.date: 08/28/2018
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables [Visual Basic]
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables [Visual Basic]
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
ms.openlocfilehash: 610f2a1020cc15f855b3ddfc0917e14aae34fb82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344934"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Introducción a LINQ en Visual Basic
Language-Integrated Query (LINQ) adds query capabilities to Visual Basic and provides simple and powerful capabilities when you work with all kinds of data. Rather than sending a query to a database to be processed, or working with different query syntax for each type of data that you are searching, LINQ introduces queries as part of the Visual Basic language. Utiliza una sintaxis unificada independientemente del tipo de datos.  
  
 LINQ enables you to query data from a SQL Server database, XML, in-memory arrays and collections, ADO.NET datasets, or any other remote or local data source that supports LINQ. You can do all this with common Visual Basic language elements. Because your queries are written in the Visual Basic language, your query results are returned as strongly-typed objects. Estos objetos son compatibles con IntelliSense, lo que le permite escribir código más rápidamente y detectar errores en las consultas en tiempo de compilación en lugar de en tiempo de ejecución. Las consultas LINQ se pueden utilizar como el origen de consultas adicionales para refinar los resultados. También se pueden enlazar a controles para que los usuarios puedan ver y modificar fácilmente los resultados de la consulta.  
  
 Por ejemplo, en el siguiente ejemplo de código se muestra una consulta LINQ que devuelve una lista de clientes de una colección y los agrupa basándose en su ubicación.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Ejecución de los ejemplos  
 To run the examples in the introduction and in the [Structure of a LINQ Query](#structure-of-a-linq-query) section, include the following code, which returns lists of customers and orders.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>LINQ providers  
 A *LINQ provider* maps your Visual Basic LINQ queries to the data source being queried. Cuando usted escribe una consulta LINQ, el proveedor toma esa consulta y la traduce en comandos que podrá ejecutar el origen de datos. El proveedor también convierte los datos del origen en los objetos que forman el resultado de su consulta. Por último, convierte los objetos en datos cuando envía actualizaciones al origen de datos.  
  
 Visual Basic includes the following LINQ providers.  
  
|Proveedor|Descripción|  
|---|---|  
|LINQ to Objects|El proveedor LINQ to Objects le permite consultar las matrices y colecciones en memoria. Si un objeto es compatible con las interfaces <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, el proveedor LINQ to Objects le permite consultarlo.<br /><br /> You can enable the LINQ to Objects provider by importing the <xref:System.Linq> namespace, which is imported by default for all Visual Basic projects.<br /><br /> For more information about the LINQ to Objects provider, see [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|El proveedor LINQ to SQL le permite consultar y modificar datos en una base de datos de SQL Server. Esto hace que sea fácil asignar el modelo de objetos de una aplicación a las tablas y los objetos de una base de datos.<br /><br /> Visual Basic makes it easier to work with LINQ to SQL by including the Object Relational Designer (O/R Designer). Este diseñador se usa para crear un modelo de objetos en una aplicación que se asigna a los objetos de una base de datos. The O/R Designer also provides functionality to map stored procedures and functions to the <xref:System.Data.Linq.DataContext> object, which manages communication with the database and stores state for optimistic concurrency checks.<br /><br /> For more information about the LINQ to SQL provider, see [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). For more information about the Object Relational Designer, see [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|El proveedor LINQ to XML le permite consultar y modificar XML. Puede modificar XML en memoria o puede cargar XML desde un archivo y guardarlo en él.<br /><br /> Additionally, the LINQ to XML provider enables XML literals and XML axis properties that enable you to write XML directly in your Visual Basic code. For more information, see [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|The LINQ to DataSet provider enables you to query and update data in an ADO.NET dataset. Puede agregar la eficacia de LINQ a las aplicaciones que utilicen conjuntos de datos con el fin de simplificar y ampliar las funcionalidades de consulta, agregado y actualización de los datos del conjunto de datos.<br /><br /> Para más información, vea [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Structure of a LINQ query  
 A LINQ query, often referred to as a *query expression*, consists of a combination of query clauses that identify the data sources and iteration variables for the query. Una expresión de consulta también incluye instrucciones para ordenar, filtrar, agrupar y combinar, o cálculos para aplicar al origen de datos. La sintaxis de las expresiones de consulta se parece a la sintaxis de SQL; por lo tanto, le puede resultar familiar gran parte de la sintaxis.  
  
 Una expresión de consulta comienza con una cláusula `From`. Esta cláusula identifica los datos de origen de una consulta y las variables que se usan para referirse individualmente a cada elemento de los datos de origen. These variables are named *range variables* or *iteration variables*. La cláusula `From` se requiere para una consulta, excepto para consultas `Aggregate`, donde la cláusula `From` es opcional. Una vez que se hayan identificado el ámbito y el origen de la consulta en las cláusulas `From` o `Aggregate`, puede incluir cualquier combinación de cláusulas de consulta para refinar la consulta. For details about query clauses, see Visual Basic LINQ Query Operators later in this topic. Por ejemplo, la siguiente consulta identifica una colección de origen de datos de cliente como la variable `customers` y una variable de iteración denominada `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 Este ejemplo es una consulta válida por sí misma; sin embargo, la consulta es mucho más eficaz cuando agrega más cláusulas de consulta para refinar los resultados. Por ejemplo, puede agregar una cláusula `Where` para filtrar los resultados mediante uno o varios valores. Las expresiones de consulta son una sola línea de código; puede simplemente anexar cláusulas de consulta adicionales al final de la consulta. You can break up a query across multiple lines of text to improve readability by using the underscore (\_) line-continuation character. En el siguiente ejemplo de código se muestra una consulta que incluye una cláusula `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Otra cláusula de consulta eficaz es la cláusula `Select`, que sólo le permite devolver los campos seleccionados del origen de datos. Las consultas LINQ devuelven colecciones enumerables de objetos fuertemente tipados. Una consulta puede devolver una colección de tipos anónimos o de tipos con nombre. Puede utilizar la cláusula `Select` para que solo se devuelva un único campo del origen de datos. Al hacerlo, el tipo de la colección devuelto es el tipo de ese campo único. También puede utilizar la cláusula `Select` para devolver varios campos del origen de datos. Al hacerlo, el tipo de la colección devuelto es un nuevo tipo anónimo. También puede hacer coincidir los campos devueltos por la consulta a los campos de un tipo con nombre especificado. En el siguiente ejemplo de código se muestra una expresión de consulta que devuelve una colección de tipos anónimos con miembros rellenados con datos de los campos seleccionados del origen de datos.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Las consultas LINQ también pueden utilizarse para combinar varios orígenes de datos y devolver un único resultado. Esto puede hacerse con una o más cláusulas `From` o mediante las cláusulas de consulta `Join` o `Group Join`. En el siguiente ejemplo de código se muestra una expresión de consulta que combina datos de clientes y pedidos y devuelve una colección de tipos anónimos que contiene datos de clientes y pedidos.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 Puede utilizar la cláusula `Group Join` para crear un resultado de consulta jerárquica que contenga una colección de objetos Customer. Cada objeto Customer tiene una propiedad que contiene una colección de todos los pedidos para ese cliente. En el siguiente ejemplo de código se muestra una expresión de consulta que combina datos de clientes y pedidos como un resultado jerárquico y devuelve una colección de tipos anónimos. La consulta devuelve un tipo que incluye una propiedad `CustomerOrders` que contiene una colección de datos de pedidos del cliente. También incluye una propiedad `OrderTotal` que contiene la suma de los totales de todos los pedidos de ese cliente. (Esta consulta es equivalente a una combinación externa izquierda).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Hay varios operadores de consulta LINQ adicionales que puede utilizar para crear expresiones de consulta eficaces. En la siguiente sección de este tema se describen las diversas cláusulas de consulta que puede incluir en una expresión de consulta. For details about Visual Basic query clauses, see [Queries](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic LINQ query operators  

Las clases en el espacio de nombres <xref:System.Linq> y los otros espacios de nombres compatibles con consultas LINQ incluyen métodos a los que puede llamar para crear y refinar las consultas en función de las necesidades de su aplicación. Visual Basic includes keywords for the following common query clauses. For details about Visual Basic query clauses, see [Queries](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>Cláusula From

Either a [`From` clause](../../../../visual-basic/language-reference/queries/from-clause.md) or an `Aggregate` clause is required to begin a query. Una cláusula `From` especifica una colección de origen y una variable de iteración de una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select (cláusula)

Opcional. A [`Select` clause](../../../../visual-basic/language-reference/queries/select-clause.md) declares a set of iteration variables for a query. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Si no se especifica una cláusula `Select`, las variables de iteración de la consulta se componen de las variables de iteración especificadas por la cláusula `From` o `Aggregate`.

### <a name="where-clause"></a>Cláusula Where

Opcional. A [`Where` clause](../../../../visual-basic/language-reference/queries/where-clause.md) specifies a filtering condition for a query. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By clause]

|Optional. An [`Order By` clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) specifies the sort order for columns in a query. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join (cláusula)

Opcional. A [`Join` clause](../../../../visual-basic/language-reference/queries/join-clause.md) combines two collections into a single collection. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By (cláusula)

Opcional. A [`Group By` clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) groups the elements of a query result. It can be used to apply aggregate functions to each group. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join (cláusula)

Opcional. A [`Group Join` clause](../../../../visual-basic/language-reference/queries/group-join-clause.md) combines two collections into a single hierarchical collection. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate (cláusula)

Either an [`Aggregate` clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) or a `From` clause is required to begin a query. Una cláusula `Aggregate` aplica una o más funciones agregadas a una colección. For example, you can use the `Aggregate` clause to calculate a sum for all the elements returned by a query, as the following example does.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

También puede utilizar la cláusula `Aggregate` para modificar una consulta. Por ejemplo, puede utilizar la cláusula `Aggregate` para realizar un cálculo en una colección de consultas relacionada. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let (cláusula)

Opcional. A [`Let` clause](../../../../visual-basic/language-reference/queries/let-clause.md) computes a value and assigns it to a new variable in the query. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct (cláusula)

Opcional. A `Distinct` clause restricts the values of the current iteration variable to eliminate duplicate values in query results. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip (cláusula)

Opcional. A [`Skip` clause](../../../../visual-basic/language-reference/queries/skip-clause.md) bypasses a specified number of elements in a collection and then returns the remaining elements. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While (cláusula)

Opcional. A [`Skip While` clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take (cláusula)

Opcional. A [`Take` clause](../../../../visual-basic/language-reference/queries/take-clause.md) returns a specified number of contiguous elements from the start of a collection. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While (cláusula)

Opcional. A [`Take While` clause](../../../../visual-basic/language-reference/queries/take-while-clause.md) includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Use additional LINQ query features  
  
Puede usar características de consulta LINQ adicionales llamando a los miembros de los tipos de enumerables y consultables proporcionados por LINQ. Puede utilizar estas funciones adicionales llamando a un operador de consulta determinado en el resultado de una expresión de consulta. For example, the following example uses the <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> method to combine the results of two queries into one query result. Utiliza el método <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> para devolver el resultado de la consulta como una lista genérica.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 For details about additional LINQ capabilities, see [Standard Query Operators Overview](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Connect to a database by using LINQ to SQL  
 In Visual Basic, you identify the SQL Server database objects, such as tables, views, and stored procedures, that you want to access by using a LINQ to SQL file. Un archivo LINQ to SQL tiene una extensión .dbml.  
  
 When you have a valid connection to a SQL Server database, you can add a **LINQ to SQL Classes** item template to your project. De este modo se mostrará el Object Relational Designer (O/R Designer). The O/R Designer enables you to drag the items that you want to access in your code from the **Server Explorer**/**Database Explorer** onto the designer surface. El archivo LINQ to SQL agrega un objeto <xref:System.Data.Linq.DataContext> al proyecto. Este objeto incluye propiedades y colecciones para las tablas y vistas a las que desea acceder y métodos para los procedimientos almacenados a los que desea llamar. Después de haber guardado los cambios en el archivo LINQ to SQL (.dbml), puede acceder a estos objetos en el código haciendo referencia al objeto <xref:System.Data.Linq.DataContext> definido por el O/R Designer. El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se determina en función del nombre del archivo LINQ to SQL. Por ejemplo, un archivo LINQ to SQL denominado Northwind.dbml creará un objeto <xref:System.Data.Linq.DataContext> denominado `NorthwindDataContext`.  
  
 For examples with step-by-step instructions, see [How to: Query a Database](how-to-query-a-database-by-using-linq.md) and [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic features that support LINQ  
 Visual Basic includes other notable features that make the use of LINQ simple and reduce the amount of code that you must write to perform LINQ queries. Entre ellas se incluyen las siguientes:  
  
- **Anonymous types**, which enable you to create a new type based on a query result.  
  
- **Implicitly typed variables**, which enable you to defer specifying a type and let the compiler infer the type based on the query result.  
  
- **Extension methods**, which enable you to extend an existing type with your own methods without modifying the type itself.  
  
 For details, see [Visual Basic Features That Support LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Deferred and immediate query execution

 La ejecución de una consulta se realiza de manera independiente con respecto a la creación de una consulta. Después de crear una consulta, un mecanismo independiente desencadena su ejecución. A query can be executed as soon as it is defined (*immediate execution*), or the definition can be stored and the query can be executed later (*deferred execution*).  
  
 De forma predeterminada, cuando crea una consulta, la propia consulta no se ejecuta inmediatamente. En su lugar, la definición de la consulta se almacena en la variable que se utiliza para hacer referencia al resultado de la consulta. Cuando se accede a la variable de resultado de la consulta más adelante en el código, como, por ejemplo, en un bucle `For…Next`, se ejecuta la consulta. This process is referred to as *deferred execution*.  
  
 Queries can also be executed when they are defined, which is referred to as *immediate execution*. Puede desencadenar la ejecución inmediata aplicando un método que requiera acceso a elementos individuales del resultado de la consulta. Esto puede ser el resultado de incluir una función de agregado, como `Count`, `Sum`, `Average`, `Min` o `Max`. For more information about aggregate functions, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md).  
  
 El uso de los métodos `ToList` o `ToArray` también fuerza la ejecución inmediata. Esto le puede resultar útil cuando desee ejecutar la consulta inmediatamente y almacenar en caché los resultados. For more information about these methods, see [Converting Data Types](../../concepts/linq/converting-data-types.md).  
  
 For more information about query execution, see [Writing Your First LINQ Query](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML en Visual Basic  
 The XML features in Visual Basic include XML literals and XML axis properties, which enable you easily to create, access, query, and modify XML in your code. Los literales XML le permiten escribir XML directamente en el código. El compilador de Visual Basic trata el XML como un objeto de datos de primera clase.  
  
 En el siguiente ejemplo de código se muestra cómo crear un elemento XML, acceder a sus subelementos y atributos y consultar el contenido del elemento mediante LINQ.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 For more information, see [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Recursos relacionados  
  
|Tema|Descripción|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Describes the XML features in Visual Basic that can be queried and that enable you to include XML as first-class data objects in your Visual Basic code.|  
|[Consultas](../../../language-reference/queries/index.md)|Provides reference information about the query clauses that are available in Visual Basic.|  
|[LINQ (Language Integrated Query)](../../concepts/linq/index.md)|Incluye información general, instrucciones de programación y ejemplos de LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Incluye información general, guía de programación y ejemplos de LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Incluye información general, guía de programación y ejemplos de LINQ to Objects.|  
|[LINQ to ADO.NET (Página de portal)](../../concepts/linq/linq-to-adonet-portal-page.md)|Includes links to general information, programming guidance, and samples for LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Incluye información general, guía de programación y ejemplos de LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>How to and walkthrough topics
 [Cómo: Consultar una base de datos](how-to-query-a-database-by-using-linq.md)  
  
 [Cómo: Llamar a un procedimiento almacenado](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Cómo: Modificar datos en una bases de datos](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Cómo: Combinar datos con cláusulas Join](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Cómo: Ordenar los resultados de una consulta](how-to-sort-query-results-by-using-linq.md)  
  
 [Cómo: Filtrar los resultados de una consulta](how-to-filter-query-results-by-using-linq.md)  
  
 [Cómo: Hacer el recuento, la suma o el promedio de datos](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Featured book chapters  
 [Chapter 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [Programming Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Vea también

- [LINQ (Language Integrated Query)](../../concepts/linq/index.md)
- [Información general sobre LINQ to XML en Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Información general de LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Herramientas LINQ to SQL en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [Métodos DataContext (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
