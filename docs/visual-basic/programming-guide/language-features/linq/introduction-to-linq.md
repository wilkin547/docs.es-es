---
title: Introducción a LINQ en Visual Basic
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
ms.openlocfilehash: 6987263854b0d0372bc08bb7e4d6efb498e265f1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973631"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Introducción a LINQ en Visual Basic
Language-Integrated Query (LINQ) agrega capacidades de consulta a Visual Basic y proporciona funcionalidades sencillas y potentes cuando se trabaja con todos los tipos de datos. En lugar de enviar una consulta a una base de datos que se procesen o trabajar con la sintaxis de consulta diferentes para cada tipo de datos que está buscando, LINQ presenta las consultas como parte del lenguaje Visual Basic. Utiliza una sintaxis unificada independientemente del tipo de datos.  
  
 LINQ permite consultar datos desde una base de datos de SQL Server, XML, las matrices en memoria y colecciones, los conjuntos de datos ADO.NET o cualquier otro origen de datos local o remoto que es compatible con LINQ. Puede hacer todo esto con elementos comunes del lenguaje Visual Basic. Dado que las consultas se escriben en el lenguaje Visual Basic, los resultados de la consulta se devuelven como objetos fuertemente tipados. Estos objetos son compatibles con IntelliSense, lo que le permite escribir código más rápidamente y detectar errores en las consultas en tiempo de compilación en lugar de en tiempo de ejecución. Las consultas LINQ se pueden utilizar como el origen de consultas adicionales para refinar los resultados. También se pueden enlazar a controles para que los usuarios puedan ver y modificar fácilmente los resultados de la consulta.  
  
 Por ejemplo, en el siguiente ejemplo de código se muestra una consulta LINQ que devuelve una lista de clientes de una colección y los agrupa basándose en su ubicación.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Ejecución de los ejemplos  
 Para ejecutar los ejemplos en la introducción y, en el [estructura de una consulta LINQ](#structure-of-a-linq-query) sección, incluya el código siguiente, que devuelve listas de clientes y pedidos.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>Proveedores LINQ  
 Un *proveedor LINQ* asigna las consultas LINQ de Visual Basic para el origen de datos que se está consultando. Cuando usted escribe una consulta LINQ, el proveedor toma esa consulta y la traduce en comandos que podrá ejecutar el origen de datos. El proveedor también convierte los datos del origen en los objetos que forman el resultado de su consulta. Por último, convierte los objetos en datos cuando envía actualizaciones al origen de datos.  
  
 Visual Basic incluye los siguientes proveedores LINQ.  
  
|Proveedor|Descripción|  
|---|---|  
|LINQ to Objects|El proveedor LINQ to Objects le permite consultar las matrices y colecciones en memoria. Si un objeto es compatible con las interfaces <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, el proveedor LINQ to Objects le permite consultarlo.<br /><br /> Puede habilitar el proveedor LINQ to Objects importando el <xref:System.Linq> espacio de nombres que se importa de forma predeterminada para todos los proyectos de Visual Basic.<br /><br /> Para obtener más información sobre el proveedor LINQ to Objects, vea [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|El proveedor LINQ to SQL le permite consultar y modificar datos en una base de datos de SQL Server. Esto hace que sea fácil asignar el modelo de objetos de una aplicación a las tablas y los objetos de una base de datos.<br /><br /> Visual Basic hace más fácil trabajar con LINQ to SQL incluyendo el Object Relational Designer (Object Relational Designer). Este diseñador se usa para crear un modelo de objetos en una aplicación que se asigna a los objetos de una base de datos. El Object Relational Designer también proporciona funcionalidad para asignar procedimientos almacenados y funciones para el <xref:System.Data.Linq.DataContext> object, que administra la comunicación con la base de datos y almacena el estado de las comprobaciones de simultaneidad optimista.<br /><br /> Para obtener más información sobre el proveedor LINQ to SQL, vea [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Para obtener más información acerca de Object Relational Designer, vea [LINQ to SQL Tools en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|El proveedor LINQ to XML le permite consultar y modificar XML. Puede modificar XML en memoria o puede cargar XML desde un archivo y guardarlo en él.<br /><br /> Además, el proveedor LINQ to XML habilita literales XML y propiedades de eje XML que le permiten escribir XML directamente en el código de Visual Basic. Para obtener más información, consulte [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|El proveedor LINQ to DataSet le permite consultar y actualizar datos en un [!INCLUDE[vstecado](~/includes/vstecado-md.md)] conjunto de datos. Puede agregar la eficacia de LINQ a las aplicaciones que utilicen conjuntos de datos con el fin de simplificar y ampliar las funcionalidades de consulta, agregado y actualización de los datos del conjunto de datos.<br /><br /> Para más información, vea [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Estructura de una consulta LINQ  
 Una consulta LINQ, conoce a menudo como un *expresión de consulta*, consta de una combinación de cláusulas de consulta que identifican los orígenes de datos y las variables de iteración de la consulta. Una expresión de consulta también incluye instrucciones para ordenar, filtrar, agrupar y combinar, o cálculos para aplicar al origen de datos. La sintaxis de las expresiones de consulta se parece a la sintaxis de SQL; por lo tanto, le puede resultar familiar gran parte de la sintaxis.  
  
 Una expresión de consulta comienza con una cláusula `From`. Esta cláusula identifica los datos de origen de una consulta y las variables que se usan para referirse individualmente a cada elemento de los datos de origen. Estas variables se denominan *las variables de rango* o *las variables de iteración*. La cláusula `From` se requiere para una consulta, excepto para consultas `Aggregate`, donde la cláusula `From` es opcional. Una vez que se hayan identificado el ámbito y el origen de la consulta en las cláusulas `From` o `Aggregate`, puede incluir cualquier combinación de cláusulas de consulta para refinar la consulta. Para obtener más información acerca de las cláusulas de consulta, vea los operadores de consulta LINQ de Visual Basic más adelante en este tema. Por ejemplo, la siguiente consulta identifica una colección de origen de datos de cliente como la variable `customers` y una variable de iteración denominada `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 Este ejemplo es una consulta válida por sí misma; sin embargo, la consulta es mucho más eficaz cuando agrega más cláusulas de consulta para refinar los resultados. Por ejemplo, puede agregar una cláusula `Where` para filtrar los resultados mediante uno o varios valores. Las expresiones de consulta son una sola línea de código; puede simplemente anexar cláusulas de consulta adicionales al final de la consulta. Puede dividir una consulta en varias líneas de texto para mejorar la legibilidad mediante el carácter de subrayado (\_) carácter de continuación de línea. En el siguiente ejemplo de código se muestra una consulta que incluye una cláusula `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Otra cláusula de consulta eficaz es la cláusula `Select`, que sólo le permite devolver los campos seleccionados del origen de datos. Las consultas LINQ devuelven colecciones enumerables de objetos fuertemente tipados. Una consulta puede devolver una colección de tipos anónimos o de tipos con nombre. Puede utilizar la cláusula `Select` para que solo se devuelva un único campo del origen de datos. Al hacerlo, el tipo de la colección devuelto es el tipo de ese campo único. También puede utilizar la cláusula `Select` para devolver varios campos del origen de datos. Al hacerlo, el tipo de la colección devuelto es un nuevo tipo anónimo. También puede hacer coincidir los campos devueltos por la consulta a los campos de un tipo con nombre especificado. En el siguiente ejemplo de código se muestra una expresión de consulta que devuelve una colección de tipos anónimos con miembros rellenados con datos de los campos seleccionados del origen de datos.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Las consultas LINQ también pueden utilizarse para combinar varios orígenes de datos y devolver un único resultado. Esto puede hacerse con una o más cláusulas `From` o mediante las cláusulas de consulta `Join` o `Group Join`. En el siguiente ejemplo de código se muestra una expresión de consulta que combina datos de clientes y pedidos y devuelve una colección de tipos anónimos que contiene datos de clientes y pedidos.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 Puede utilizar la cláusula `Group Join` para crear un resultado de consulta jerárquica que contenga una colección de objetos Customer. Cada objeto Customer tiene una propiedad que contiene una colección de todos los pedidos para ese cliente. En el siguiente ejemplo de código se muestra una expresión de consulta que combina datos de clientes y pedidos como un resultado jerárquico y devuelve una colección de tipos anónimos. La consulta devuelve un tipo que incluye una propiedad `CustomerOrders` que contiene una colección de datos de pedidos del cliente. También incluye una propiedad `OrderTotal` que contiene la suma de los totales de todos los pedidos de ese cliente. (Esta consulta es equivalente a una combinación externa izquierda).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Hay varios operadores de consulta LINQ adicionales que puede utilizar para crear expresiones de consulta eficaces. En la siguiente sección de este tema se describen las diversas cláusulas de consulta que puede incluir en una expresión de consulta. Para obtener más información acerca de las cláusulas de consulta de Visual Basic, vea [consultas](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Operadores de consulta LINQ de Visual Basic  

Las clases en el espacio de nombres <xref:System.Linq> y los otros espacios de nombres compatibles con consultas LINQ incluyen métodos a los que puede llamar para crear y refinar las consultas en función de las necesidades de su aplicación. Visual Basic incluye palabras clave para las siguientes cláusulas de consulta común. Para obtener más información acerca de las cláusulas de consulta de Visual Basic, vea [consultas](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>Cláusula From

Ya sea un [ `From` cláusula](../../../../visual-basic/language-reference/queries/from-clause.md) o un `Aggregate` cláusula es necesario para iniciar una consulta. Una cláusula `From` especifica una colección de origen y una variable de iteración de una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select (cláusula)

Opcional. Un [ `Select` cláusula](../../../../visual-basic/language-reference/queries/select-clause.md) declara un conjunto de variables de iteración de una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Si no se especifica una cláusula `Select`, las variables de iteración de la consulta se componen de las variables de iteración especificadas por la cláusula `From` o `Aggregate`.

### <a name="where-clause"></a>Cláusula Where

Opcional. Un [ `Where` cláusula](../../../../visual-basic/language-reference/queries/where-clause.md) especifica una condición de filtrado para una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Cláusula Order By]

| Opcional. Un [ `Order By` cláusula](../../../../visual-basic/language-reference/queries/order-by-clause.md) especifica el criterio de ordenación de columnas en una consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join (cláusula)

Opcional. Un [ `Join` cláusula](../../../../visual-basic/language-reference/queries/join-clause.md) combina dos colecciones en una sola colección. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By (cláusula)

Opcional. Un [ `Group By` cláusula](../../../../visual-basic/language-reference/queries/group-by-clause.md) agrupa los elementos de un resultado de la consulta. Puede usar para aplicar funciones de agregado a cada grupo. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join (cláusula)

Opcional. Un [ `Group Join` cláusula](../../../../visual-basic/language-reference/queries/group-join-clause.md) combina dos colecciones en una sola colección jerárquica. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate (cláusula)

Ya sea un [ `Aggregate` cláusula](../../../../visual-basic/language-reference/queries/aggregate-clause.md) o un `From` cláusula es necesario para iniciar una consulta. Una cláusula `Aggregate` aplica una o más funciones agregadas a una colección. Por ejemplo, puede usar el `Aggregate` cláusula para calcular una suma de todos los elementos devueltos por una consulta, como el siguiente ejemplo.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

También puede utilizar la cláusula `Aggregate` para modificar una consulta. Por ejemplo, puede utilizar la cláusula `Aggregate` para realizar un cálculo en una colección de consultas relacionada. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let (cláusula)

Opcional. Un [ `Let` cláusula](../../../../visual-basic/language-reference/queries/let-clause.md) calcula un valor y lo asigna a una nueva variable en la consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct (cláusula)

Opcional. Un `Distinct` cláusula restringe los valores de la variable de iteración actual para eliminar valores duplicados en los resultados de la consulta. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip (cláusula)

Opcional. Un [ `Skip` cláusula](../../../../visual-basic/language-reference/queries/skip-clause.md) omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While (cláusula)

Opcional. Un [ `Skip While` cláusula](../../../../visual-basic/language-reference/queries/skip-while-clause.md) omite los elementos de una colección como una condición especificada sea `true` y, a continuación, devuelve los elementos restantes. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take (cláusula)

Opcional. Un [ `Take` cláusula](../../../../visual-basic/language-reference/queries/take-clause.md) devuelve un número especificado de elementos contiguos desde el principio de una colección. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While (cláusula)

Opcional. Un [ `Take While` cláusula](../../../../visual-basic/language-reference/queries/take-while-clause.md) incluye los elementos de una colección como una condición especificada sea `true` y omite los elementos restantes. Por ejemplo:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Usar las características de consulta LINQ adicionales  
  
Puede usar características de consulta LINQ adicionales llamando a los miembros de los tipos de enumerables y consultables proporcionados por LINQ. Puede utilizar estas funciones adicionales llamando a un operador de consulta determinado en el resultado de una expresión de consulta. Por ejemplo, en el ejemplo siguiente se utiliza el <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> método para combinar los resultados de dos consultas en el resultado de una consulta. Utiliza el método <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> para devolver el resultado de la consulta como una lista genérica.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 Para obtener más información acerca de las capacidades adicionales de LINQ, vea [Standard Query Operators Overview](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Conectarse a una base de datos mediante LINQ to SQL  
 En Visual Basic, identifique los objetos de base de datos de SQL Server, como tablas, vistas y procedimientos almacenados, que se desean tener acceso mediante el uso de LINQ a archivo SQL. Un archivo LINQ to SQL tiene una extensión .dbml.  
  
 Cuando haya una conexión válida a una base de datos de SQL Server, puede agregar un **clases LINQ to SQL** plantilla de elemento al proyecto. De este modo se mostrará el Object Relational Designer (O/R Designer). El Object Relational Designer le permite arrastrar los elementos que desee tener acceso en el código desde el **Explorador de servidores**/**Database Explorer** a la superficie del diseñador. El archivo LINQ to SQL agrega un objeto <xref:System.Data.Linq.DataContext> al proyecto. Este objeto incluye propiedades y colecciones para las tablas y vistas a las que desea acceder y métodos para los procedimientos almacenados a los que desea llamar. Después de haber guardado los cambios en el archivo LINQ to SQL (.dbml), puede acceder a estos objetos en el código haciendo referencia al objeto <xref:System.Data.Linq.DataContext> definido por el O/R Designer. El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se determina en función del nombre del archivo LINQ to SQL. Por ejemplo, un archivo LINQ to SQL denominado Northwind.dbml creará un objeto <xref:System.Data.Linq.DataContext> denominado `NorthwindDataContext`.  
  
 Para obtener ejemplos con instrucciones paso a paso, vea [Cómo: Consultar una base de datos](how-to-query-a-database-by-using-linq.md) y [Cómo: Llamar a un procedimiento almacenado](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Características de Visual Basic que admiten LINQ  
 Visual Basic incluye otras características destacables que simplifican el uso de LINQ y reducen la cantidad de código que se debe escribir para realizar consultas LINQ. Entre ellas se incluyen las siguientes:  
  
-   **Tipos anónimos**, que le permiten crear un nuevo tipo basado en un resultado de la consulta.  
  
-   **Las variables con tipo implícito**, que le permiten aplazar la especificación de un tipo y permiten que el compilador infiera el tipo según el resultado de la consulta.  
  
-   **Métodos de extensión**, que le permiten extender un tipo existente con sus propios métodos sin modificar el propio tipo.  
  
 Para obtener más información, consulte [LINQ de soporte técnico que las características de Visual Basic](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Ejecución de consultas aplazadas e inmediatas

 La ejecución de una consulta se realiza de manera independiente con respecto a la creación de una consulta. Después de crear una consulta, un mecanismo independiente desencadena su ejecución. Se puede ejecutar una consulta tan pronto como se define (*ejecución inmediata*), o se puede almacenar la definición y la consulta se puede ejecutar más adelante (*ejecución aplazada*).  
  
 De forma predeterminada, cuando crea una consulta, la propia consulta no se ejecuta inmediatamente. En su lugar, la definición de la consulta se almacena en la variable que se utiliza para hacer referencia al resultado de la consulta. Cuando se accede a la variable de resultado de la consulta más adelante en el código, como, por ejemplo, en un bucle `For…Next`, se ejecuta la consulta. Este proceso se conoce como *ejecución aplazada*.  
  
 También se pueden ejecutar las consultas cuando se definen, que se conoce como *ejecución inmediata*. Puede desencadenar la ejecución inmediata aplicando un método que requiera acceso a elementos individuales del resultado de la consulta. Esto puede ser el resultado de incluir una función de agregado, como `Count`, `Sum`, `Average`, `Min` o `Max`. Para obtener más información acerca de las funciones de agregado, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md).  
  
 El uso de los métodos `ToList` o `ToArray` también fuerza la ejecución inmediata. Esto le puede resultar útil cuando desee ejecutar la consulta inmediatamente y almacenar en caché los resultados. Para obtener más información acerca de estos métodos, consulte [convertir tipos de datos](../../concepts/linq/converting-data-types.md).  
  
 Para obtener más información acerca de la ejecución de consultas, vea [escribir su primera consulta con LINQ](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML en Visual Basic  
 Las características XML en Visual Basic incluyen literales XML y propiedades de eje XML, lo que permite fácilmente crear, acceden, consultar y modificar XML en el código. Los literales XML le permiten escribir XML directamente en el código. El compilador de Visual Basic trata el XML como un objeto de datos de primera clase.  
  
 En el siguiente ejemplo de código se muestra cómo crear un elemento XML, acceder a sus subelementos y atributos y consultar el contenido del elemento mediante LINQ.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Para obtener más información, consulte [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Recursos relacionados  
  
|Tema|Descripción|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Describe las características XML en Visual Basic que se puede consultar y que permiten incluir XML como objetos de datos de primera clase en su código Visual Basic.|  
|[Consultas](../../../language-reference/queries/index.md)|Proporciona información de referencia acerca de las cláusulas de consulta que están disponibles en Visual Basic.|  
|[LINQ (Language Integrated Query)](../../concepts/linq/index.md)|Incluye información general, instrucciones de programación y ejemplos de LINQ.|  
|[LINQ to SQL](~/docs/framework/data/adonet/sql/linq/index.md)|Incluye información general, guía de programación y ejemplos de LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Incluye información general, guía de programación y ejemplos de LINQ to Objects.|  
|[LINQ to ADO.NET (Página de portal)](../../concepts/linq/linq-to-adonet-portal-page.md)|Incluye vínculos a información general, Guía de programación y ejemplos de LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Incluye información general, guía de programación y ejemplos de LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>Cómo y temas del tutorial
 [Cómo: Consultar una base de datos](how-to-query-a-database-by-using-linq.md)  
  
 [Cómo: Llamar a un procedimiento almacenado](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Cómo: Modificar datos en una base de datos](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Cómo: Combinar datos con cláusulas JOIN](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Cómo: Ordenar resultados de consulta](how-to-sort-query-results-by-using-linq.md)  
  
 [Cómo: Filtrar los resultados de consulta](how-to-filter-query-results-by-using-linq.md)  
  
 [Cómo: Recuento, suma o promedio de datos](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Cómo: Buscar el valor mínimo o máximo en un resultado de consulta](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Capítulos destacados del libro  
 [Capítulo 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) en [de programación Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Vea también

- [LINQ (Language Integrated Query)](../../concepts/linq/index.md)
- [Información general sobre LINQ to XML en Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Información general de LINQ to DataSet](~/docs/framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](~/docs/framework/data/adonet/sql/linq/index.md)
- [Herramientas LINQ to SQL en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [Métodos DataContext (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
