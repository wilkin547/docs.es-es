---
title: "Escribir la primera consulta con LINQ (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [LINQ en Visual Basic], escritura"
  - "consultas LINQ [Visual Basic]"
  - "LINQ [Visual Basic], escritura de consultas"
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: 56
caps.handback.revision: 54
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Escribir la primera consulta con LINQ (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una *consulta* es una expresión que recupera datos de un origen de datos.  Las consultas se expresan en un lenguaje de consultas dedicado.  A lo largo del tiempo se han ido desarrollando lenguajes diferentes para los distintos tipos de orígenes de datos, como SQL para las bases de datos relacionales y XQuery para XML.  De esta manera, el desarrollador de aplicaciones debe aprender un nuevo lenguaje de consultas para cada tipo de origen de datos o formato de datos admitido.  
  
 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] simplifica esta situación al proporcionar un modelo coherente para trabajar con los datos de varios formatos y orígenes de datos.  En una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], siempre se trabaja con objetos.  Se utilizan los mismos modelos de codificación básicos para consultar y transformar los datos de documentos XML, bases de datos SQL, conjuntos de datos y entidades de ADO.NET, colecciones de .NET Framework y cualquier otro formato u origen de datos para el que haya un proveedor [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] disponible.  En este documento se describen las tres fases para crear y utilizar consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] básicas.  
  
 ![vínculo a vídeo](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Para obtener una demostración de vídeo relacionada, vea [How Do I: Get Started with LINQ?](http://go.microsoft.com/fwlink/?LinkId=133021).  
  
## Las tres etapas de una operación de consulta  
 Las operaciones de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] se componen de tres acciones:  
  
1.  Obtención de uno o varios orígenes de datos.  
  
2.  Creación de la consulta.  
  
3.  Ejecución de la consulta.  
  
 En [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], la ejecución y la creación de una consulta son operaciones distintas.  Por el simple hecho de crear una consulta, no se recuperan datos.  Este punto se analiza con más detalle más adelante, en este mismo tema.  
  
 En el ejemplo siguiente se muestran las tres partes de una operación de consulta.  En el ejemplo se utiliza una matriz de enteros como origen de datos, cómodo a efectos de demostración.  Sin embargo, los mismos conceptos también se aplican a otros orígenes de datos.  
  
> [!NOTE]
>  En [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que **Option Infer** está establecido en **En**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Resultado:  
  
 `0 2 4 6`  
  
## El origen de datos  
 Dado que el origen de datos del ejemplo anterior es una matriz, se admite implícitamente la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>.  Es este hecho lo que permite utilizar una matriz como origen de datos para una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  Tipos que <xref:System.Collections.Generic.IEnumerable%601> admiten o una interfaz derivada como <xref:System.Linq.IQueryable%601> genérico se denomina *los tipos* que se pueden consultar.  
  
 Como tipo que se puede consultar implícitamente, la matriz no requiere modificaciones ni un tratamiento especial para actuar como origen de datos [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  Lo mismo sucede con cualquier tipo de colección que admita <xref:System.Collections.Generic.IEnumerable%601>, incluidos <xref:System.Collections.Generic.List%601> genérico, <xref:System.Collections.Generic.Dictionary%602>, y otras clases de la biblioteca de clases de .NET Framework.  
  
 Si los datos de origen no ya implementan <xref:System.Collections.Generic.IEnumerable%601>, un proveedor de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] es necesario implementar la funcionalidad *de los operadores de consulta* estándar para ese origen de datos.  Por ejemplo, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] controla el trabajo de cargar un documento XML en un tipo <xref:System.Xml.Linq.XElement> que se pueda consultar, como se muestra en el ejemplo siguiente.  Para obtener más información sobre los operadores de consulta estándar, vea [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Con [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], primero se crea una asignación relacional de objetos en tiempo de diseño, ya sea manualmente o mediante el [Object Relational Designer](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2).  Después, se escriben las consultas en los objetos y, en tiempo de ejecución, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] controla la comunicación con la base de datos.  En el ejemplo siguiente, `customers` representa una tabla concreta de la base de datos y <xref:System.Data.Linq.Table%601> admite la interfaz genérica <xref:System.Linq.IQueryable%601>.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Para obtener más información sobre cómo crear tipos de orígenes de datos específicos, consulte la documentación de los distintos proveedores [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  \(Para obtener una lista de estos proveedores, vea [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).\) La regla básica es simple: un origen de datos [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] es cualquier objeto que admite la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> o una interfaz que herede de ella.  
  
> [!NOTE]
>  También se pueden utilizar tipos como <xref:System.Collections.ArrayList>, que admite la interfaz no genérica <xref:System.Collections.IEnumerable>, como orígenes de datos [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  Para obtener un ejemplo donde se usa <xref:System.Collections.ArrayList>, vea [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md).  
  
## La consulta  
 En la consulta se especifica qué información se desea recuperar del origen o de los orígenes de datos.  También tiene la opción de especificar cómo se debería ordenar, agrupar o estructurar esa información antes de devolverse.  Para habilitar la creación de consultas, Visual Basic incorpora nueva sintaxis de consulta en el lenguaje.  
  
 Cuando se ejecuta, la consulta del ejemplo siguiente devuelve todos los números pares de una matriz de enteros, `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 La expresión de consulta contiene tres cláusulas: `From`, `Where` y `Select`.  La función y el propósito específicos de cada una de las cláusulas de las expresiones de consulta se analiza en [Operaciones básicas de consulta \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  Para obtener más información, vea [Consultas](../../../../visual-basic/language-reference/queries/queries.md).  Observe que en [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] una definición de consulta suele almacenarse en una variable y se ejecuta después.  La variable de consulta, como `evensQuery` en el ejemplo anterior, debe ser un tipo que se puede consultar. El tipo de `evensQuery` es `IEnumerable(Of Integer)`, asignado por el compilador mediante la inferencia de tipo de variable local.  
  
 Es importante recordar que la propia variable de consulta no realiza ninguna acción ni devuelve datos.  Sólo almacena la definición de la consulta.  En el ejemplo anterior, es el bucle `For Each` el que ejecuta la consulta.  
  
## Ejecución de la consulta  
 La ejecución de la consulta es proceso independiente de su creación.  La creación de la consulta la define, pero su ejecución la desencadena un mecanismo diferente.  Se puede ejecutar un consulta en cuanto esté definida \(*ejecución inmediata*\), o se puede guardar la definición y ejecutar la consulta más tarde \(*ejecución aplazada*\).  
  
### Ejecución diferida  
 Una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] típica se parece a la del ejemplo anterior, en el que se define `evensQuery`.  En él se crea la consulta, pero no se ejecuta de inmediato.  La definición de la consulta se almacena en la variable de consulta `evensQuery`.  La consulta se ejecuta más adelante, normalmente mediante un bucle `For Each`, que devuelve una secuencia de valores, o aplicando un operador de consulta estándar, como `Count` o `Max`.  Este proceso se denomina *ejecución aplazada*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Para una secuencia de valores, se tiene acceso a los datos recuperados mediante la variable de iteración del bucle `For Each` \(`number` en el ejemplo anterior\).  Dado que la variable de consulta, `evensQuery`, contiene la definición de la consulta en lugar de los resultados, puede ejecutar una consulta tantas veces como desee, utilizando la variable de consulta.  Por ejemplo, podría tener una base de datos en su aplicación que sea actualizada continuamente por una aplicación independiente.  Después de haber creado una consulta que recupere los datos de esa base de datos, puede utilizar un bucle `For Each` para ejecutar la consulta una y otra vez, recuperando en cada ocasión los datos más recientes.  
  
 En el siguiente ejemplo se muestra cómo funciona la ejecución diferida.  Una vez definida `evensQuery2` y ejecutada con un bucle `For Each`, como en los ejemplos anteriores, algunos elementos del origen de datos `numbers` cambian.  A continuación, un segundo bucle `For Each` vuelve a ejecutar `evensQuery2`.  Los resultados son diferentes la segunda vez, porque el bucle `For Each` ejecuta la consulta otra vez, utilizando los nuevos valores de `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Resultado:  
  
 `Evens in original array:`  
  
 `0 2 4 6`  
  
 `Evens in changed array:`  
  
 `0 10 2 22 8`  
  
### Ejecución inmediata  
 En la ejecución diferida de consultas, la definición de la consulta se almacena en una variable de consulta para su posterior ejecución.  En la ejecución inmediata, la consulta se ejecuta en el momento de su definición.  La ejecución se activa al aplicar un método que requiere acceso a los elementos individuales del resultado de la consulta.  La ejecución inmediata se fuerza mediante el uso de uno de los operadores de consulta estándar que devuelven valores únicos.  Algunos ejemplos son `Count`, `Max`, `Average` y `First`.  Estos operadores de consulta estándar ejecutan la consulta en cuanto se aplican para calcular y devolver un resultado singleton.  Para obtener más información sobre los operadores de consulta estándar que devuelven valores únicos, vea [Aggregation Operations](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md), [Element Operations](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md) y [Quantifier Operations](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).  
  
 La consulta siguiente devuelve un recuento de los números pares de una matriz de enteros.  La definición de la consulta no se guarda y `numEvens` es un `Integer` simple.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Se puede conseguir el mismo resultado utilizando el método `Aggregate`.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 También puede forzar la ejecución de una consulta llamando al método `ToList` o `ToArray` en una consulta \(ejecución inmediata\) o variable de consulta \(ejecución diferida\), como se muestra en el código siguiente.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 En los ejemplos anteriores, `evensQuery3` es una variable de consulta, pero `evensList` es una lista y `evensArray` es una matriz.  
  
 El uso de `ToList` o `ToArray` para forzar la ejecución inmediata es especialmente útil cuando se desea ejecutar la consulta inmediatamente y almacenar los resultados en memoria caché en un objeto de colección único.  Para obtener más información sobre estos métodos, vea [Converting Data Types](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 También puede provocar la ejecución de una consulta mediante el uso de un método `IEnumerable`, como el método <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>.  
  
## Demostraciones de vídeo relacionadas  
 [How Do I: Get Started with LINQ?](http://go.microsoft.com/fwlink/?LinkId=133021)  
  
 [Video How to: Writing Queries in Visual Basic](http://go.microsoft.com/fwlink/?LinkID=100356)  
  
## Vea también  
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Ejemplos de LINQ](../Topic/LINQ%20Samples.md)   
 [Información general sobre Object Relational Designer](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio1.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)