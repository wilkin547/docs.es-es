---
title: "Introduction to LINQ Queries (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "deferred execution [LINQ]"
  - "LINQ, queries"
  - "LINQ, deferred execution"
  - "queries [LINQ], about LINQ queries"
ms.assetid: 37895c02-268c-41d5-be39-f7d936fa88a8
caps.latest.revision: 47
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 45
---
# Introduction to LINQ Queries (C#)
Una *consulta* es una expresión que recupera datos de un origen de datos.  Las consultas normalmente se expresan en un lenguaje de consultas especializado.  A lo largo del tiempo se han ido desarrollando lenguajes diferentes para los distintos tipos de orígenes de datos, como SQL para las bases de datos relacionales y XQuery para XML.  Por tanto, los desarrolladores han tenido que aprender un nuevo lenguaje de consulta para cada tipo de origen de datos o formato de datos que deben usar.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] simplifica esta situación al proporcionar un modelo coherente para trabajar con los datos de varios tipos de formatos y orígenes de datos.  En una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], siempre se trabaja con objetos.  Se utilizan los mismos modelos de codificación básicos para consultar y transformar datos de documentos XML, bases de datos SQL, conjuntos de datos [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)], colecciones .NET y cualquier otro formato para el que haya disponible un proveedor [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  
  
## Las tres partes de una operación de consulta  
 Todas las operaciones de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] se componen de tres acciones distintas:  
  
1.  Obtención del origen de datos.  
  
2.  Creación de la consulta.  
  
3.  Ejecución de la consulta.  
  
 En el ejemplo siguiente se muestra cómo se expresan las tres partes de una operación de consulta en el código fuente.  En el ejemplo se utiliza por comodidad una matriz de enteros como origen de datos, pero los mismos conceptos se aplican a otros orígenes de datos.  En el resto del tema se hace referencia a este ejemplo.  
  
 [!code-cs[CsLINQGettingStarted#1](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_1.cs)]  
  
 En la siguiente ilustración se muestra la operación de consulta completa.  En [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], la ejecución de la consulta es distinta de la propia consulta; en otras palabras, no se recuperan datos con la simple creación de la variable de consulta.  
  
 ![Completar operación de consulta LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq-query.png "LINQ\_Query")  
  
## El origen de datos  
 En el ejemplo anterior, como el origen de datos es una matriz, se admite implícitamente la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>.  Este hecho implica que se puede consultar con [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Una consulta se ejecuta en una instrucción `foreach` y `foreach` requiere <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>.  Los tipos que admiten <xref:System.Collections.Generic.IEnumerable%601> o una interfaz derivada, como la genérica <xref:System.Linq.IQueryable%601>, se conocen como *tipos que se pueden consultar*.  
  
 Un tipo que se puede consultar no requiere ninguna modificación o tratamiento especial para servir como origen de datos [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Si los datos de origen aún no están en memoria como tipo que se puede consultar, el proveedor [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] debe representarlos como tales.  Por ejemplo, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] carga un documento XML en un tipo <xref:System.Xml.Linq.XElement> que se puede consultar:  
  
 [!code-cs[CsLINQGettingStarted#2](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_2.cs)]  
  
 Con [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], primero se crea una asignación relacional de objetos en tiempo de diseño, ya sea manualmente o mediante el [Object Relational Designer](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2).  Después, se escriben las consultas en los objetos y, en tiempo de ejecución, [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] controla la comunicación con la base de datos.  En el ejemplo siguiente, `Customers` representa una tabla concreta de la base de datos y el tipo del resultado de la consulta, <xref:System.Linq.IQueryable%601>, se deriva de <xref:System.Collections.Generic.IEnumerable%601>.  
  
```c#  
Northwnd db = new Northwnd(@"c:\northwnd.mdf");  
  
// Query for customers in London.  
IQueryable<Customer> custQuery =  
    from cust in db.Customers  
    where cust.City == "London"  
    select cust;  
  
```  
  
 Para obtener más información sobre cómo crear tipos de orígenes de datos específicos, consulte la documentación de los distintos proveedores [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Sin embargo, la regla básica es muy simple: un origen de datos [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] es cualquier objeto que admite la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> o una interfaz que herede de ella.  
  
> [!NOTE]
>  También se pueden utilizar tipos como <xref:System.Collections.ArrayList>, que admite la interfaz no genérica <xref:System.Collections.IEnumerable>, como origen de datos [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Para obtener más información, vea [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md).  
  
##  <a name="query"></a> La consulta  
 La consulta especifica qué información se va a recuperar de uno o varios orígenes de datos.  Opcionalmente, una consulta también especifica cómo debería ordenarse, agruparse y darse forma a esa información antes de ser devuelta.  Una consulta se almacena en una variable de consulta y se inicializa con una expresión de consulta.  Para simplificar la escritura de consultas, C\# incluye nueva sintaxis de consulta.  
  
 La consulta del ejemplo anterior devuelve todos los números pares de la matriz de enteros.  La expresión de consulta contiene tres cláusulas: `from`, `where` y `select`. \(Si está familiarizado con SQL, habrá observado que el orden de las cláusulas se invierte respecto al orden de SQL.\) La cláusula `from` especifica el origen de datos, la cláusula `where` aplica el filtro y la cláusula `select` especifica el tipo de los elementos devueltos.  Ésta y las demás cláusulas de consulta se analizan con detalle en la sección [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md).  Aquí, lo importante es que, en [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)], la propia variable de consulta no realiza ninguna acción ni devuelve datos.  Simplemente almacena la información necesaria para generar los resultados cuando la consulta se ejecute posteriormente.  Para obtener más información sobre cómo se construyen las consultas en segundo plano, vea [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
> [!NOTE]
>  Las consultas también se pueden expresar con sintaxis de método.  Para obtener más información, vea [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## Ejecución de la consulta  
  
### Ejecución diferida  
 Como se ha mencionado previamente, la variable de consulta sólo almacena los comandos de la consulta.  La ejecución real de la consulta se aplaza hasta que se procese una iteración en la variable de consulta, en una instrucción `foreach`.  Este concepto se conoce como *ejecución diferida* y se muestra en el ejemplo siguiente:  
  
 [!code-cs[csLinqGettingStarted#4](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_3.cs)]  
  
 La instrucción `foreach` es también donde se recuperan los resultados de la consulta.  Por ejemplo, en la consulta anterior, la variable de iteración `num` contiene cada valor \(de uno en uno\) en la secuencia devuelta.  
  
 Dado que la propia variable de consulta nunca contiene los resultados de la consulta, se puede ejecutar tantas veces como se desee.  Por ejemplo, puede que una aplicación independiente actualice continuamente una base de datos.  En su aplicación, podría crear una consulta que recuperase los datos más recientes, y podría ejecutarla repetidamente cada cierto tiempo para recuperar cada vez resultados diferentes.  
  
### Forzar la ejecución inmediata  
 Las consultas que realizan funciones de agregación en un intervalo de elementos de origen primero deben recorrer en iteración dichos elementos.  Algunos ejemplos de esas consultas son `Count`, `Max`, `Average` y `First`.  Se ejecutan sin una instrucción `foreach` explícita porque la propia consulta debe utilizar `foreach` para devolver un resultado.  Debe saber también que estos tipos de consultas devuelven un solo valor, no una colección `IEnumerable`.  La consulta siguiente devuelve un recuento de los números pares de la matriz de origen:  
  
 [!code-cs[csLinqGettingStarted#5](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_4.cs)]  
  
 Para forzar la ejecución inmediata de cualquier consulta y almacenar en memoria caché sus resultados, puede llamar al método <xref:System.Linq.Enumerable.ToList%2A> o <xref:System.Linq.Enumerable.ToArray%2A>.  
  
 [!code-cs[csLinqGettingStarted#6](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_5.cs)]  
  
 También puede forzar la ejecución si coloca el bucle `foreach` justo después de la expresión de consulta.  Sin embargo, al llamar a `ToList` o `ToArray` también se almacenan en memoria caché todos los datos en un objeto de colección único.  
  
## Vea también  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)   
 [Ejemplos de LINQ](../Topic/LINQ%20Samples.md)   
 [Información general sobre Object Relational Designer](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio1.md)   
 [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [foreach, in](../../../../csharp/language-reference/keywords/foreach-in.md)   
 [Palabras clave para consultas \(LINQ\)](../../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ and Deferred Execution Video](http://go.microsoft.com/fwlink/?LinkId=112414)