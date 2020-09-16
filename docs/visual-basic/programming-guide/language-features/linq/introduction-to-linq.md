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
ms.openlocfilehash: 97602b7341636219382b6a405c678bc458ef146a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556751"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Introducción a LINQ en Visual Basic
Language-Integrated Query (LINQ) agrega capacidades de consulta a Visual Basic y proporciona funcionalidades sencillas y eficaces cuando se trabaja con todos los tipos de datos. En lugar de enviar una consulta a una base de datos que se va a procesar o trabajar con una sintaxis de consulta diferente para cada tipo de datos que se está buscando, LINQ presenta las consultas como parte del lenguaje Visual Basic. Utiliza una sintaxis unificada independientemente del tipo de datos.  
  
 LINQ permite consultar datos de una base de datos SQL Server, XML, matrices y colecciones en memoria, conjuntos de datos ADO.NET o cualquier otro origen de datos remoto o local que admita LINQ. Puede hacer todo esto con los elementos de lenguaje de Visual Basic comunes. Dado que las consultas se escriben en el lenguaje Visual Basic, los resultados de la consulta se devuelven como objetos fuertemente tipados. Estos objetos son compatibles con IntelliSense, lo que le permite escribir código más rápidamente y detectar errores en las consultas en tiempo de compilación en lugar de en tiempo de ejecución. Las consultas LINQ se pueden utilizar como el origen de consultas adicionales para refinar los resultados. También se pueden enlazar a controles para que los usuarios puedan ver y modificar fácilmente los resultados de la consulta.  
  
 Por ejemplo, en el siguiente ejemplo de código se muestra una consulta LINQ que devuelve una lista de clientes de una colección y los agrupa basándose en su ubicación.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Ejecución de los ejemplos  
 Para ejecutar los ejemplos de la introducción y en la [estructura de una consulta LINQ](#structure-of-a-linq-query) , incluya el siguiente código, que devuelve listas de clientes y pedidos.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>Proveedores LINQ  
 Un *proveedor LINQ* asigna las consultas LINQ Visual Basic al origen de datos que se consulta. Cuando usted escribe una consulta LINQ, el proveedor toma esa consulta y la traduce en comandos que podrá ejecutar el origen de datos. El proveedor también convierte los datos del origen en los objetos que forman el resultado de su consulta. Por último, convierte los objetos en datos cuando envía actualizaciones al origen de datos.  
  
 Visual Basic incluye los siguientes proveedores LINQ.  
  
|Proveedor|Descripción|  
|---|---|  
|LINQ to Objects|El proveedor LINQ to Objects le permite consultar las matrices y colecciones en memoria. Si un objeto es compatible con las interfaces <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, el proveedor LINQ to Objects le permite consultarlo.<br /><br /> Puede habilitar el proveedor de LINQ to Objects importando el <xref:System.Linq> espacio de nombres, que se importa de forma predeterminada para todos los proyectos de Visual Basic.<br /><br /> Para obtener más información sobre el proveedor de LINQ to Objects, vea [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|El proveedor LINQ to SQL le permite consultar y modificar datos en una base de datos de SQL Server. Esto hace que sea fácil asignar el modelo de objetos de una aplicación a las tablas y los objetos de una base de datos.<br /><br /> Visual Basic facilita el trabajo con LINQ to SQL incluyendo el Object Relational Designer (Object Relational Designer). Este diseñador se usa para crear un modelo de objetos en una aplicación que se asigna a los objetos de una base de datos. Object Relational Designer también proporciona funcionalidad para asignar procedimientos almacenados y funciones al <xref:System.Data.Linq.DataContext> objeto, que administra la comunicación con la base de datos y almacena el estado de las comprobaciones de simultaneidad optimista.<br /><br /> Para obtener más información sobre el proveedor de LINQ to SQL, vea [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Para obtener más información sobre el Object Relational Designer, vea [herramientas de LINQ to SQL en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|El proveedor LINQ to XML le permite consultar y modificar XML. Puede modificar XML en memoria o puede cargar XML desde un archivo y guardarlo en él.<br /><br /> Además, el proveedor de LINQ to XML habilita literales XML y propiedades de eje XML que le permiten escribir XML directamente en el código de Visual Basic. Para obtener más información, vea [XML](../xml/index.md).|  
|LINQ to DataSet|El proveedor de LINQ to DataSet permite consultar y actualizar datos en un conjunto de datos de ADO.NET. Puede agregar la eficacia de LINQ a las aplicaciones que utilicen conjuntos de datos con el fin de simplificar y ampliar las funcionalidades de consulta, agregado y actualización de los datos del conjunto de datos.<br /><br /> Para más información, vea [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Estructura de una consulta LINQ  
 Una consulta LINQ, a la que se suele hacer referencia como una *expresión de consulta*, consta de una combinación de cláusulas de consulta que identifican los orígenes de datos y las variables de iteración de la consulta. Una expresión de consulta también incluye instrucciones para ordenar, filtrar, agrupar y combinar, o cálculos para aplicar al origen de datos. La sintaxis de las expresiones de consulta se parece a la sintaxis de SQL; por lo tanto, le puede resultar familiar gran parte de la sintaxis.  
  
 Una expresión de consulta comienza con una cláusula `From`. Esta cláusula identifica los datos de origen de una consulta y las variables que se usan para referirse individualmente a cada elemento de los datos de origen. Estas variables se denominan *variables de rango* o *variables de iteración*. La cláusula `From` se requiere para una consulta, excepto para consultas `Aggregate`, donde la cláusula `From` es opcional. Una vez que se hayan identificado el ámbito y el origen de la consulta en las cláusulas `From` o `Aggregate`, puede incluir cualquier combinación de cláusulas de consulta para refinar la consulta. Para obtener más información sobre las cláusulas de consulta, vea Visual Basic operadores de consulta LINQ más adelante en este tema. Por ejemplo, la siguiente consulta identifica una colección de origen de datos de cliente como la variable `customers` y una variable de iteración denominada `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 Este ejemplo es una consulta válida por sí misma; sin embargo, la consulta es mucho más eficaz cuando agrega más cláusulas de consulta para refinar los resultados. Por ejemplo, puede agregar una cláusula `Where` para filtrar los resultados mediante uno o varios valores. Las expresiones de consulta son una sola línea de código; puede simplemente anexar cláusulas de consulta adicionales al final de la consulta. Puede dividir una consulta en varias líneas de texto para mejorar la legibilidad mediante el uso del \_ carácter de continuación de línea de subrayado (). En el siguiente ejemplo de código se muestra una consulta que incluye una cláusula `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Otra cláusula de consulta eficaz es la cláusula `Select`, que sólo le permite devolver los campos seleccionados del origen de datos. Las consultas LINQ devuelven colecciones enumerables de objetos fuertemente tipados. Una consulta puede devolver una colección de tipos anónimos o de tipos con nombre. Puede utilizar la cláusula `Select` para que solo se devuelva un único campo del origen de datos. Al hacerlo, el tipo de la colección devuelto es el tipo de ese campo único. También puede utilizar la cláusula `Select` para devolver varios campos del origen de datos. Al hacerlo, el tipo de la colección devuelto es un nuevo tipo anónimo. También puede hacer coincidir los campos devueltos por la consulta a los campos de un tipo con nombre especificado. En el siguiente ejemplo de código se muestra una expresión de consulta que devuelve una colección de tipos anónimos con miembros rellenados con datos de los campos seleccionados del origen de datos.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Las consultas LINQ también pueden utilizarse para combinar varios orígenes de datos y devolver un único resultado. Esto puede hacerse con una o más cláusulas `From` o mediante las cláusulas de consulta `Join` o `Group Join`. En el siguiente ejemplo de código se muestra una expresión de consulta que combina datos de clientes y pedidos y devuelve una colección de tipos anónimos que contiene datos de clientes y pedidos.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 Puede utilizar la cláusula `Group Join` para crear un resultado de consulta jerárquica que contenga una colección de objetos Customer. Cada objeto Customer tiene una propiedad que contiene una colección de todos los pedidos para ese cliente. En el siguiente ejemplo de código se muestra una expresión de consulta que combina datos de clientes y pedidos como un resultado jerárquico y devuelve una colección de tipos anónimos. La consulta devuelve un tipo que incluye una propiedad `CustomerOrders` que contiene una colección de datos de pedidos del cliente. También incluye una propiedad `OrderTotal` que contiene la suma de los totales de todos los pedidos de ese cliente. (Esta consulta es equivalente a una combinación externa izquierda).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Hay varios operadores de consulta LINQ adicionales que puede utilizar para crear expresiones de consulta eficaces. En la siguiente sección de este tema se describen las diversas cláusulas de consulta que puede incluir en una expresión de consulta. Para obtener más información sobre las cláusulas de consulta de Visual Basic, vea [consultas](../../../language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic operadores de consulta LINQ  

Las clases en el espacio de nombres <xref:System.Linq> y los otros espacios de nombres compatibles con consultas LINQ incluyen métodos a los que puede llamar para crear y refinar las consultas en función de las necesidades de su aplicación. Visual Basic incluye palabras clave para las siguientes cláusulas de consulta comunes. Para obtener más información sobre las cláusulas de consulta de Visual Basic, vea [consultas](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>Cláusula From

Se requiere una [ `From` cláusula](../../../language-reference/queries/from-clause.md) o una `Aggregate` cláusula para iniciar una consulta. Una cláusula `From` especifica una colección de origen y una variable de iteración de una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select (cláusula)

Opcional. Una [ `Select` cláusula](../../../language-reference/queries/select-clause.md) declara un conjunto de variables de iteración para una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Si no se especifica una cláusula `Select`, las variables de iteración de la consulta se componen de las variables de iteración especificadas por la cláusula `From` o `Aggregate`.

### <a name="where-clause"></a>Cláusula WHERE

Opcional. Una [ `Where` cláusula](../../../language-reference/queries/where-clause.md) especifica una condición de filtrado para una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By (cláusula)

Opcional. Una [ `Order By` cláusula](../../../language-reference/queries/order-by-clause.md) especifica el criterio de ordenación de las columnas de una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join (cláusula)

Opcional. Una [ `Join` cláusula](../../../language-reference/queries/join-clause.md) combina dos colecciones en una sola colección. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By (cláusula)

Opcional. Una [ `Group By` cláusula](../../../language-reference/queries/group-by-clause.md) agrupa los elementos del resultado de una consulta. Se puede usar para aplicar funciones de agregado a cada grupo. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join (cláusula)

Opcional. Una [ `Group Join` cláusula](../../../language-reference/queries/group-join-clause.md) combina dos colecciones en una sola colección jerárquica. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate (cláusula)

Se requiere una [ `Aggregate` cláusula](../../../language-reference/queries/aggregate-clause.md) o una `From` cláusula para iniciar una consulta. Una cláusula `Aggregate` aplica una o más funciones agregadas a una colección. Por ejemplo, puede utilizar la `Aggregate` cláusula para calcular una suma de todos los elementos devueltos por una consulta, como hace el siguiente ejemplo.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

También puede utilizar la cláusula `Aggregate` para modificar una consulta. Por ejemplo, puede utilizar la cláusula `Aggregate` para realizar un cálculo en una colección de consultas relacionada. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let (cláusula)

Opcional. Una [ `Let` cláusula](../../../language-reference/queries/let-clause.md) calcula un valor y lo asigna a una nueva variable en la consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct (cláusula)

Opcional. Una `Distinct` cláusula restringe los valores de la variable de iteración actual para eliminar los valores duplicados en los resultados de la consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip (cláusula)

Opcional. Una [ `Skip` cláusula](../../../language-reference/queries/skip-clause.md) omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While (cláusula)

Opcional. Una [ `Skip While` cláusula](../../../language-reference/queries/skip-while-clause.md) omite los elementos de una colección siempre que una condición especificada sea `true` y, a continuación, devuelve los elementos restantes. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take (cláusula)

Opcional. Una [ `Take` cláusula](../../../language-reference/queries/take-clause.md) devuelve un número especificado de elementos contiguos desde el principio de una colección. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While (cláusula)

Opcional. Una [ `Take While` cláusula](../../../language-reference/queries/take-while-clause.md) incluye los elementos de una colección siempre que una condición especificada sea `true` y omita los elementos restantes. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Usar características de consulta LINQ adicionales  
  
Puede usar características de consulta LINQ adicionales llamando a los miembros de los tipos de enumerables y consultables proporcionados por LINQ. Puede utilizar estas funciones adicionales llamando a un operador de consulta determinado en el resultado de una expresión de consulta. Por ejemplo, en el ejemplo siguiente se usa el <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> método para combinar los resultados de dos consultas en el resultado de una consulta. Utiliza el método <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> para devolver el resultado de la consulta como una lista genérica.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 Para obtener más información acerca de las funcionalidades adicionales de LINQ, consulte [información general sobre operadores de consulta estándar](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Conectarse a una base de datos mediante LINQ to SQL  
 En Visual Basic, se identifican los objetos de base de datos de SQL Server, como tablas, vistas y procedimientos almacenados, a los que se desea obtener acceso mediante un archivo de LINQ to SQL. Un archivo LINQ to SQL tiene una extensión .dbml.  
  
 Si tiene una conexión válida a una base de datos de SQL Server, puede Agregar una plantilla de elementos de **LINQ to SQL clases** al proyecto. De este modo se mostrará el Object Relational Designer (O/R Designer). El Object Relational Designer le permite arrastrar los elementos a los que desea obtener acceso en el código desde el **Explorador de servidores** / **Explorador de bases de datos** en la superficie del diseñador. El archivo LINQ to SQL agrega un objeto <xref:System.Data.Linq.DataContext> al proyecto. Este objeto incluye propiedades y colecciones para las tablas y vistas a las que desea acceder y métodos para los procedimientos almacenados a los que desea llamar. Después de haber guardado los cambios en el archivo LINQ to SQL (.dbml), puede acceder a estos objetos en el código haciendo referencia al objeto <xref:System.Data.Linq.DataContext> definido por el O/R Designer. El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se determina en función del nombre del archivo LINQ to SQL. Por ejemplo, un archivo LINQ to SQL denominado Northwind.dbml creará un objeto <xref:System.Data.Linq.DataContext> denominado `NorthwindDataContext`.  
  
 Para obtener ejemplos con instrucciones paso a paso, consulte [Cómo: consultar una base de datos](how-to-query-a-database-by-using-linq.md) y [Cómo: llamar a un procedimiento almacenado](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic características compatibles con LINQ  
 Visual Basic incluye otras características destacables que facilitan el uso de LINQ y reducen la cantidad de código que debe escribir para realizar consultas LINQ. Entre ellas, se incluyen las siguientes:  
  
- **Tipos anónimos**, que permiten crear un nuevo tipo basado en el resultado de una consulta.  
  
- **Variables con tipo implícito**, que permiten aplazar la especificación de un tipo y permitir que el compilador infiera el tipo basándose en el resultado de la consulta.  
  
- **Métodos de extensión**, que permiten extender un tipo existente con sus propios métodos sin modificar el propio tipo.  
  
 Para obtener más información, vea [Visual Basic características compatibles con LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Ejecución de consultas diferida e inmediata

 La ejecución de una consulta se realiza de manera independiente con respecto a la creación de una consulta. Después de crear una consulta, un mecanismo independiente desencadena su ejecución. Una consulta se puede ejecutar en cuanto se define (*ejecución inmediata*) o se puede almacenar la definición y la consulta se puede ejecutar más adelante (*ejecución aplazada*).  
  
 De forma predeterminada, cuando crea una consulta, la propia consulta no se ejecuta inmediatamente. En su lugar, la definición de la consulta se almacena en la variable que se utiliza para hacer referencia al resultado de la consulta. Cuando se accede a la variable de resultado de la consulta más adelante en el código, como, por ejemplo, en un bucle `For…Next`, se ejecuta la consulta. Este proceso se conoce como *ejecución aplazada*.  
  
 Las consultas también se pueden ejecutar cuando se definen, lo que se conoce como *ejecución inmediata*. Puede desencadenar la ejecución inmediata aplicando un método que requiera acceso a elementos individuales del resultado de la consulta. Esto puede ser el resultado de incluir una función de agregado, como `Count`, `Sum`, `Average`, `Min` o `Max`. Para obtener más información sobre las funciones de agregado, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md).  
  
 El uso de los métodos `ToList` o `ToArray` también fuerza la ejecución inmediata. Esto le puede resultar útil cuando desee ejecutar la consulta inmediatamente y almacenar en caché los resultados. Para obtener más información sobre estos métodos, vea [convertir tipos de datos](../../concepts/linq/converting-data-types.md).  
  
 Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML en Visual Basic  
 Las características XML de Visual Basic incluyen literales XML y propiedades de eje XML, lo que le permite crear fácilmente, tener acceso, consultar y modificar XML en el código. Los literales XML le permiten escribir XML directamente en el código. El compilador de Visual Basic trata el XML como un objeto de datos de primera clase.  
  
 En el siguiente ejemplo de código se muestra cómo crear un elemento XML, acceder a sus subelementos y atributos y consultar el contenido del elemento mediante LINQ.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Para obtener más información, vea [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Recursos relacionados  
  
|Tema|Descripción|  
|---|---|  
|[XML](../xml/index.md)|Describe las características XML de Visual Basic que se pueden consultar y que permiten incluir XML como objetos de datos de primera clase en el código Visual Basic.|  
|[Consultas](../../../language-reference/queries/index.md)|Proporciona información de referencia sobre las cláusulas de consulta que están disponibles en Visual Basic.|  
|[LINQ (Language Integrated Query)](../../concepts/linq/index.md)|Incluye información general, instrucciones de programación y ejemplos de LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Incluye información general, guía de programación y ejemplos de LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Incluye información general, guía de programación y ejemplos de LINQ to Objects.|  
|[LINQ to ADO.NET (Página de portal)](../../concepts/linq/linq-to-adonet-portal-page.md)|Incluye vínculos a información general, guía de programación y ejemplos de LINQ to ADO.NET.|  
|[LINQ to XML](../../../../standard/linq/linq-xml-overview.md)|Incluye información general, guía de programación y ejemplos de LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>Temas de procedimientos y tutoriales
 [Cómo: Consultar una base de datos](how-to-query-a-database-by-using-linq.md)  
  
 [Cómo: Llamar a un procedimiento almacenado](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Cómo: Modificar datos en una bases de datos](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Cómo: Combinar datos con cláusulas Join](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Cómo: Ordenar los resultados de una consulta](how-to-sort-query-results-by-using-linq.md)  
  
 [Cómo: Filtrar los resultados de una consulta](how-to-filter-query-results-by-using-linq.md)  
  
 [Cómo: Hacer el recuento, la suma o el promedio de datos](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Capítulos destacados del libro  
 [Capítulo 17: LINQ](/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) en [programación Visual Basic 2008](/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Vea también

- [LINQ (Language Integrated Query)](../../concepts/linq/index.md)
- [Información general sobre LINQ to XML en Visual Basic](../xml/overview-of-linq-to-xml.md)
- [Información general de LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Herramientas LINQ to SQL en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [DataContext (Métodos) (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
