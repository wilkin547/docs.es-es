---
title: "Introducción a LINQ en Visual Basic | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
caps.latest.revision: 28
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e1343b06089df63beb73cbb27a38de396f5cb6c8
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-linq-in-visual-basic"></a>Introducción a LINQ en Visual Basic
Language-Integrated Query (LINQ) agrega capacidades de consulta a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] y proporciona funcionalidades sencillas y potentes cuando se trabaja con todo tipo de datos. En lugar de enviar una consulta a una base de datos para su procesamiento o de trabajar con distintas sintaxis de consulta para cada tipo de datos que esté buscando, LINQ presenta las consultas como parte del lenguaje [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Utiliza una sintaxis unificada independientemente del tipo de datos.  
  
 LINQ permite consultar datos de una base de datos de SQL Server, XML, en la memoria matrices y colecciones, [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] origen de conjuntos de datos o cualquier otro dato local o remoto compatible con LINQ. Todo esto puede hacerse mediante elementos comunes del lenguaje [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Dado que las consultas se escriben en el lenguaje [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], los resultados de la consulta se devuelven como objetos fuertemente tipados. Estos objetos son compatibles con IntelliSense, lo que le permite escribir código más rápidamente y detectar errores en las consultas en tiempo de compilación en lugar de en tiempo de ejecución. Las consultas LINQ se pueden utilizar como el origen de consultas adicionales para refinar los resultados. También se pueden enlazar a controles para que los usuarios puedan ver y modificar fácilmente los resultados de la consulta.  
  
 Por ejemplo, en el siguiente ejemplo de código se muestra una consulta LINQ que devuelve una lista de clientes de una colección y los agrupa basándose en su ubicación.  
  
 [!code-vb[1 VbVbalrIntroToLINQ](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_1.vb)]  
  
 En este tema encontrará información acerca de las siguientes áreas:  
  
-   [Ejecución de ejemplos](#RunningtheExamples)  
  
-   [Proveedores LINQ](#LINQProviders)  
  
-   [Estructura de una consulta LINQ](#StructureOfALINQQuery)  
  
-   [Operadores de consulta LINQ de Visual Basic](#VisualBasicLINQQueryOperators)  
  
-   [Conectarse a una base de datos mediante LINQ to SQL](#ConnectingToADatabase)  
  
-   [Características de Visual Basic que admiten LINQ](#VisualBasicFeaturesThatSupportLINQ)  
  
-   [Ejecución de consultas aplazadas e inmediatas](#QueryExecution)  
  
-   [XML en Visual Basic](#XMLInVisualBasic)  
  
-   [Recursos relacionados](#RelatedResources)  
  
-   [Cómo y temas del tutorial](#HowToAndWalkthroughTopics)  
  
##  <a name="RunningtheExamples"></a>Ejecución de ejemplos  
 Para ejecutar los ejemplos en la introducción y en la sección “Estructura de una consulta LINQ”, incluya el siguiente código, que devuelve listas de clientes y pedidos.  
  
 [!code-vb[VbVbalrIntroToLINQ&#31;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_2.vb)]  
  
##  <a name="LINQProviders"></a>Proveedores LINQ  
 Un *proveedor LINQ* asigna su [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] consultas LINQ para el origen de datos que se está consultando. Cuando usted escribe una consulta LINQ, el proveedor toma esa consulta y la traduce en comandos que podrá ejecutar el origen de datos. El proveedor también convierte los datos del origen en los objetos que forman el resultado de su consulta. Por último, convierte los objetos en datos cuando envía actualizaciones al origen de datos.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] incluye los siguientes proveedores LINQ.  
  
|Provider|Descripción|  
|---|---|  
|LINQ to Objects|El proveedor LINQ to Objects le permite consultar las matrices y colecciones en memoria. Si un objeto admite la <xref:System.Collections.IEnumerable>o <xref:System.Collections.Generic.IEnumerable%601>interfaz, el proveedor LINQ to Objects permite consultar lo</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable><br /><br /> Puede habilitar el proveedor LINQ to Objects importando el <xref:System.Linq>espacio de nombres que se importa de forma predeterminada para todos los [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proyectos.</xref:System.Linq><br /><br /> Para obtener más información sobre el proveedor LINQ to Objects, vea [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9).|  
|LINQ to SQL|El proveedor LINQ to SQL le permite consultar y modificar datos en una base de datos de SQL Server. Esto hace que sea fácil asignar el modelo de objetos de una aplicación a las tablas y los objetos de una base de datos.<br /><br /> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] facilita el trabajo con LINQ to SQL incluyendo el Object Relational Designer (O/R Designer). Este diseñador se usa para crear un modelo de objetos en una aplicación que se asigna a los objetos de una base de datos. El Object Relational Designer también proporciona funcionalidad para asignar procedimientos almacenados y funciones a la <xref:System.Data.Linq.DataContext>object, que administra la comunicación con la base de datos y almacena el estado de las comprobaciones de simultaneidad optimista.</xref:System.Data.Linq.DataContext><br /><br /> Para obtener más información sobre el proveedor LINQ to SQL, vea [LINQ to SQL](https://msdn.microsoft.com/library/bb386976). Para obtener más información acerca de Object Relational Designer, vea [LINQ to SQL Tools en Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|El proveedor LINQ to XML le permite consultar y modificar XML. Puede modificar XML en memoria o puede cargar XML desde un archivo y guardarlo en él.<br /><br /> Además, el proveedor LINQ to XML habilita literales XML y propiedades de eje XML que le permiten escribir XML directamente en su código de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Para obtener más información, consulte [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|El proveedor LINQ to DataSet permite consultar y actualizar datos en un [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] conjunto de datos. Puede agregar la eficacia de LINQ a las aplicaciones que utilicen conjuntos de datos con el fin de simplificar y ampliar las funcionalidades de consulta, agregado y actualización de los datos del conjunto de datos.<br /><br /> Para obtener más información, consulte [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17).|  
  
##  <a name="StructureOfALINQQuery"></a>Estructura de una consulta LINQ  
 Una consulta LINQ, que suele denominarse una *expresión de consulta*, consta de una combinación de cláusulas de consulta que identifican los orígenes de datos y las variables de iteración de la consulta. Una expresión de consulta también incluye instrucciones para ordenar, filtrar, agrupar y combinar, o cálculos para aplicar al origen de datos. La sintaxis de las expresiones de consulta se parece a la sintaxis de SQL; por lo tanto, le puede resultar familiar gran parte de la sintaxis.  
  
 Una expresión de consulta comienza con una cláusula `From`. Esta cláusula identifica los datos de origen de una consulta y las variables que se usan para referirse individualmente a cada elemento de los datos de origen. Estas variables se denominan *variables de intervalo* o *variables de iteración*. La cláusula `From` se requiere para una consulta, excepto para consultas `Aggregate`, donde la cláusula `From` es opcional. Una vez que se hayan identificado el ámbito y el origen de la consulta en las cláusulas `From` o `Aggregate`, puede incluir cualquier combinación de cláusulas de consulta para refinar la consulta. Para obtener más información acerca de las cláusulas de consulta, vea los Operadores de consulta LINQ de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] más adelante en este tema. Por ejemplo, la siguiente consulta identifica una colección de origen de datos de cliente como la variable `customers` y una variable de iteración denominada `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ&#2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_3.vb)]  
  
 Este ejemplo es una consulta válida por sí misma; sin embargo, la consulta es mucho más eficaz cuando agrega más cláusulas de consulta para refinar los resultados. Por ejemplo, puede agregar una cláusula `Where` para filtrar los resultados mediante uno o varios valores. Las expresiones de consulta son una sola línea de código; puede simplemente anexar cláusulas de consulta adicionales al final de la consulta. Puede dividir una consulta en varias líneas de texto para mejorar su legibilidad mediante el carácter de continuación de línea de subrayado (_). En el siguiente ejemplo de código se muestra una consulta que incluye una cláusula `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ&3;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_4.vb)]  
  
 Otra cláusula de consulta eficaz es la cláusula `Select`, que sólo le permite devolver los campos seleccionados del origen de datos. Las consultas LINQ devuelven colecciones enumerables de objetos fuertemente tipados. Una consulta puede devolver una colección de tipos anónimos o de tipos con nombre. Puede utilizar la cláusula `Select` para que solo se devuelva un único campo del origen de datos. Al hacerlo, el tipo de la colección devuelto es el tipo de ese campo único. También puede utilizar la cláusula `Select` para devolver varios campos del origen de datos. Al hacerlo, el tipo de la colección devuelto es un nuevo tipo anónimo. También puede hacer coincidir los campos devueltos por la consulta a los campos de un tipo con nombre especificado. En el siguiente ejemplo de código se muestra una expresión de consulta que devuelve una colección de tipos anónimos con miembros rellenados con datos de los campos seleccionados del origen de datos.  
  
 [!code-vb[VbVbalrIntroToLINQ Nº&4;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_5.vb)]  
  
 Las consultas LINQ también pueden utilizarse para combinar varios orígenes de datos y devolver un único resultado. Esto puede hacerse con una o más cláusulas `From` o mediante las cláusulas de consulta `Join` o `Group Join`. En el siguiente ejemplo de código se muestra una expresión de consulta que combina datos de clientes y pedidos y devuelve una colección de tipos anónimos que contiene datos de clientes y pedidos.  
  
 [!code-vb[VbVbalrIntroToLINQ&#5;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_6.vb)]  
  
 Puede utilizar la cláusula `Group Join` para crear un resultado de consulta jerárquica que contenga una colección de objetos Customer. Cada objeto Customer tiene una propiedad que contiene una colección de todos los pedidos para ese cliente. En el siguiente ejemplo de código se muestra una expresión de consulta que combina datos de clientes y pedidos como un resultado jerárquico y devuelve una colección de tipos anónimos. La consulta devuelve un tipo que incluye una propiedad `CustomerOrders` que contiene una colección de datos de pedidos del cliente. También incluye una propiedad `OrderTotal` que contiene la suma de los totales de todos los pedidos de ese cliente. (Esta consulta es equivalente a una combinación externa izquierda).  
  
 [!code-vb[VbVbalrIntroToLINQ Nº&6;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_7.vb)]  
  
 Hay varios operadores de consulta LINQ adicionales que puede utilizar para crear expresiones de consulta eficaces. En la siguiente sección de este tema se describen las diversas cláusulas de consulta que puede incluir en una expresión de consulta. Para obtener más información acerca de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] las cláusulas de consulta, vea [consultas](../../../../visual-basic/language-reference/queries/queries.md).  
  
##  <a name="VisualBasicLINQQueryOperators"></a>Operadores de consulta LINQ de Visual Basic  
 Las clases en el <xref:System.Linq>espacio de nombres y los otros espacios de nombres que admiten consultas LINQ incluyen métodos que se pueden llamar para crear y ajustar las consultas según las necesidades de su aplicación.</xref:System.Linq> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] incluye palabras clave para las cláusulas de consulta más comunes, tal como se describe en la siguiente tabla.  
  
|Término|Definición|  
|---|---|  
|[From (cláusula)](../../../../visual-basic/language-reference/queries/from-clause.md)|Para iniciar una consulta, se requiere una cláusula `From` o `Aggregate`. Una cláusula `From` especifica una colección de origen y una variable de iteración de una consulta. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#7;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_8.vb)]|  
|[Select (cláusula)](../../../../visual-basic/language-reference/queries/select-clause.md)|Opcional. Declara un conjunto de variables de iteración de una consulta. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ Nº&8;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_9.vb)]<br /><br /> Si no se especifica una cláusula `Select`, las variables de iteración de la consulta se componen de las variables de iteración especificadas por la cláusula `From` o `Aggregate`.|  
|[Where (cláusula)](../../../../visual-basic/language-reference/queries/where-clause.md)|Opcional. Especifica una condición de filtrado para una consulta. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#9;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_10.vb)]|  
|[Order By (cláusula)](../../../../visual-basic/language-reference/queries/order-by-clause.md)|Opcional. Especifica el criterio de ordenación de columnas en una consulta. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#10;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_11.vb)]|  
|[Join (cláusula)](../../../../visual-basic/language-reference/queries/join-clause.md)|Opcional. Combina dos colecciones en una sola colección. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#11;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_12.vb)]|  
|[Group By (cláusula)](../../../../visual-basic/language-reference/queries/group-by-clause.md)|Opcional. Agrupa los elementos de los resultados de una consulta. Se puede utilizar para aplicar funciones de agregado a cada grupo. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#12;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_13.vb)]|  
|[Group Join (cláusula)](../../../../visual-basic/language-reference/queries/group-join-clause.md)|Opcional. Combina dos colecciones en una sola colección jerárquica. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#13;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_14.vb)]|  
|[Aggregate (cláusula)](../../../../visual-basic/language-reference/queries/aggregate-clause.md)|Para iniciar una consulta, se requiere una cláusula `From` o `Aggregate`. Una cláusula `Aggregate` aplica una o más funciones agregadas a una colección. Por ejemplo, puede utilizar la cláusula `Aggregate` para calcular una suma de todos los elementos devueltos por una consulta.<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#14;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_15.vb)]<br /><br /> También puede utilizar la cláusula `Aggregate` para modificar una consulta. Por ejemplo, puede utilizar la cláusula `Aggregate` para realizar un cálculo en una colección de consultas relacionada.<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#15;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_16.vb)]|  
|[Let (cláusula)](../../../../visual-basic/language-reference/queries/let-clause.md)|Opcional. Calcula un valor y lo asigna a una nueva variable en la consulta. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ Nº&16;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_17.vb)]|  
|[Distinct (cláusula)](../../../../visual-basic/language-reference/queries/distinct-clause.md)|Opcional. Restringe los valores de la variable de iteración actual para eliminar los valores duplicados en los resultados de la consulta. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#17;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_18.vb)]|  
|[Skip (cláusula)](../../../../visual-basic/language-reference/queries/skip-clause.md)|Opcional. Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#18;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_19.vb)]|  
|[Skip While (cláusula)](../../../../visual-basic/language-reference/queries/skip-while-clause.md)|Opcional. Omite los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, devuelve los elementos restantes. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ Nº&19;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_20.vb)]|  
|[Take (cláusula)](../../../../visual-basic/language-reference/queries/take-clause.md)|Opcional. Devuelve un número especificado de elementos contiguos desde el principio de una colección. Por ejemplo:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#20;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_21.vb)]|  
|[Take While (cláusula)](../../../../visual-basic/language-reference/queries/take-while-clause.md)|Opcional. Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes. Por ejemplo:<br /><br /> [!code-vb[21 VbVbalrIntroToLINQ](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_22.vb)]|  
  
 Para obtener más información acerca de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] las cláusulas de consulta, vea [consultas](../../../../visual-basic/language-reference/queries/queries.md).  
  
 Puede usar características de consulta LINQ adicionales llamando a los miembros de los tipos de enumerables y consultables proporcionados por LINQ. Puede utilizar estas funciones adicionales llamando a un operador de consulta determinado en el resultado de una expresión de consulta. Por ejemplo, el siguiente ejemplo de código utiliza el <xref:System.Linq.Enumerable.Union%2A>método para combinar los resultados de dos consultas en el resultado de una consulta.</xref:System.Linq.Enumerable.Union%2A> Utiliza el <xref:System.Linq.Enumerable.ToList%2A>para devolver el resultado de la consulta como una lista genérica.</xref:System.Linq.Enumerable.ToList%2A>  
  
 [!code-vb[VbVbalrIntroToLINQ&#22;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_23.vb)]  
  
 Para obtener más información sobre las funciones adicionales de LINQ, vea [información general sobre operadores de consulta estándar](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
##  <a name="ConnectingToADatabase"></a>Conectarse a una base de datos mediante LINQ to SQL  
 En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], usted identifica los objetos de base de datos de SQL Server, como tablas, vistas y procedimientos almacenados, a los que desea acceder mediante un archivo LINQ to SQL. Un archivo LINQ to SQL tiene una extensión .dbml.  
  
 Cuando haya una conexión válida a una base de datos de SQL Server, puede agregar un **clases LINQ to SQL** plantilla de elemento al proyecto. De este modo se mostrará el Object Relational Designer (O/R Designer). El Object Relational Designer permite arrastrar los elementos que desea tener acceso en el código de la **Explorador de servidores**/**Database Explorer** a la superficie del diseñador. El archivo de LINQ to SQL agrega un <xref:System.Data.Linq.DataContext>objeto a su proyecto.</xref:System.Data.Linq.DataContext> Este objeto incluye propiedades y colecciones para las tablas y vistas a las que desea acceder y métodos para los procedimientos almacenados a los que desea llamar. Después de guardar los cambios en el archivo de LINQ to SQL (.dbml), puede tener acceso a estos objetos en el código hace referencia a la <xref:System.Data.Linq.DataContext>objeto definido por el Object Relational Designer.</xref:System.Data.Linq.DataContext> La <xref:System.Data.Linq.DataContext>objeto para su proyecto se denomina según el nombre de su archivo de LINQ to SQL.</xref:System.Data.Linq.DataContext> Por ejemplo, un archivo de LINQ to SQL que se denomina Northwind.dbml creará un <xref:System.Data.Linq.DataContext>objeto denominado `NorthwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
 Para obtener ejemplos con instrucciones paso a paso, consulte [Cómo: consultar una base de datos](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md) y [Cómo: llamar a un procedimiento almacenado](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md).  
  
##  <a name="VisualBasicFeaturesThatSupportLINQ"></a>Características de Visual Basic que admiten LINQ  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] incluye otras características destacables que simplifican el uso de LINQ y reducen la cantidad de código que debe escribir para realizar consultas LINQ. Entre ellas se incluyen las siguientes:  
  
-   **Tipos anónimos**, que permiten crear un nuevo tipo basado en un resultado de consulta.  
  
-   **Las variables de tipo implícito**, que permiten aplazar la especificación de un tipo y permitir que el compilador infiera el tipo basándose en el resultado de la consulta.  
  
-   **Métodos de extensión**, que permiten extender un tipo existente con sus propios métodos sin modificar el propio tipo.  
  
 Para obtener más información, consulte [características de Visual Basic que LINQ soporte](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md).  
  
##  <a name="QueryExecution"></a>Ejecución de consultas aplazadas e inmediatas  
 La ejecución de una consulta se realiza de manera independiente con respecto a la creación de una consulta. Después de crear una consulta, un mecanismo independiente desencadena su ejecución. Se puede ejecutar una consulta tan pronto como se define (*ejecución inmediata*), o se puede almacenar la definición y la consulta puede ejecutarse más adelante (*ejecución aplazada*).  
  
 De forma predeterminada, cuando crea una consulta, la propia consulta no se ejecuta inmediatamente. En su lugar, la definición de la consulta se almacena en la variable que se utiliza para hacer referencia al resultado de la consulta. Cuando se accede a la variable de resultado de la consulta más adelante en el código, como, por ejemplo, en un bucle `For…Next`, se ejecuta la consulta. Este proceso se conoce como *ejecución aplazada*.  
  
 Las consultas también se ejecutan cuando se definen, que se conoce como *ejecución inmediata*. Puede desencadenar la ejecución inmediata aplicando un método que requiera acceso a elementos individuales del resultado de la consulta. Esto puede ser el resultado de incluir una función de agregado, como `Count`, `Sum`, `Average`, `Min` o `Max`. Para obtener más información acerca de las funciones de agregado, consulte [cláusula Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 El uso de los métodos `ToList` o `ToArray` también fuerza la ejecución inmediata. Esto le puede resultar útil cuando desee ejecutar la consulta inmediatamente y almacenar en caché los resultados. Para obtener más información acerca de estos métodos, consulte [convertir tipos de datos](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Para obtener más información acerca de la ejecución de la consulta, vea [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
##  <a name="XMLInVisualBasic"></a>XML en Visual Basic  
 Las características XML de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] incluyen literales XML y propiedades de eje XML, que le permiten crear, acceder, consultar y modificar XML fácilmente en el código. Los literales XML le permiten escribir XML directamente en el código. El compilador de Visual Basic trata el XML como un objeto de datos de primera clase.  
  
 En el siguiente ejemplo de código se muestra cómo crear un elemento XML, acceder a sus subelementos y atributos y consultar el contenido del elemento mediante LINQ.  
  
 [!code-vb[VbXmlSamples Nº&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/introduction-to-linq_24.vb)]  
  
 Para obtener más información, consulte [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).  
  
##  <a name="RelatedResources"></a>Recursos relacionados  
  
|Tema|Descripción|  
|---|---|  
|[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)|Describe las características XML de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] que se puede consultar y que le permiten incluir XML como objetos de datos de primera clase en su código [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].|  
|[Consultas](../../../../visual-basic/language-reference/queries/queries.md)|Proporciona información de referencia acerca de las cláusulas de consulta disponibles en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].|  
|[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)|Incluye información general, instrucciones de programación y ejemplos de LINQ.|  
|[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)|Incluye información general, guía de programación y ejemplos de LINQ to SQL.|  
|[LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)|Incluye información general, guía de programación y ejemplos de LINQ to Objects.|  
|[LINQ to ADO.NET (Página de portal)](http://msdn.microsoft.com/library/dd7d3c6a-ff98-47e9-a1a7-2d4cfc42d150)|Incluye vínculos a información general, guía de programación y ejemplos de LINQ to [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)].|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)|Incluye información general, guía de programación y ejemplos de LINQ to XML.|  
  
##  <a name="HowToAndWalkthroughTopics"></a>Cómo y temas del tutorial  
 [Cómo: consultar una base de datos](how-to-query-a-database-by-using-linq.md)  
  
 [Cómo: llamar a un procedimiento almacenado](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Cómo: modificar datos en una base de datos](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Cómo: combinar datos con cláusulas JOIN](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Cómo: ordenar los resultados de la consulta](how-to-sort-query-results-by-using-linq.md)  
  
 [Cómo: filtrar los resultados de consulta](how-to-filter-query-results-by-using-linq.md)  
  
 [Cómo: recuento, suma o promedio de datos](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Cómo: buscar el valor mínimo o máximo en un resultado de consulta](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Cómo: asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)  
  
## <a name="featured-book-chapters"></a>Capítulos destacados del libro  
 [Capítulo 17: LINQ](http://go.microsoft.com/fwlink/?LinkId=195277) en [de programación Visual Basic 2008](http://go.microsoft.com/fwlink/?LinkId=195383)  
  
## <a name="see-also"></a>Vea también  
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)   
 [Información general de LINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)   
 [Información general del conjunto de datos LINQ to](http://msdn.microsoft.com/library/dc20a8fb-03f6-4b68-9c2b-7f7299e3070b)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
 [LINQ to SQL Tools en Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)   
 [Métodos de DataContext (Object Relational Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)
