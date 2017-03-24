---
title: "Walkthrough: Writing Queries in C# (LINQ) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "get-started-article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], walkthroughs"
  - "LINQ [C#], writing queries"
  - "queries [LINQ in C#], writing"
  - "writing LINQ queries"
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
caps.latest.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Walkthrough: Writing Queries in C# (LINQ)
Este tutorial muestra las características del lenguaje C\# que se utilizan para escribir expresiones de consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Después de completar este tutorial, estará preparado para ver los ejemplos y la documentación del proveedor [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] específico que le interese, como [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] to DataSets o [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  
  
## Requisitos previos  
 Este tutorial requiere características que se introducen en Visual Studio 2008.  
  
 ![vínculo a vídeo](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Para obtener una versión en vídeo de este tema, vea [Video How to: Writing Queries in C\# \(LINQ\)](http://go.microsoft.com/fwlink/?LinkId=100393).  
  
## Crear un proyecto de C\#  
  
#### Para crear un proyecto  
  
1.  Inicie Visual Studio.  
  
2.  En la barra de menú, elija **Archivo**, **Nuevo**, **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto**.  
  
3.  Expanda **Instalado**, expanda **Plantillas**, expanda **Visual c\#** y, a continuación **Aplicación de consola**.  
  
4.  En el cuadro de texto **Nombre**, escriba un nombre diferente o acepte el nombre predeterminado, y elija el botón **Aceptar**.  
  
     El nuevo proyecto aparecerá en el **Explorador de soluciones**.  
  
5.  Observe que su proyecto tiene una referencia a System.Core.dll y una directiva `using` para el espacio de nombres <xref:System.Linq?displayProperty=fullName>.  
  
## Crear un origen de datos en memoria  
 El origen de datos de las consultas es una simple lista de objetos `Student`.  Cada registro `Student` tiene un nombre, un apellido y una matriz de enteros que representa sus puntuaciones de exámenes en la clase.  Copie este código en el proyecto.  Observe las siguientes características:  
  
-   La clase `Student` está formada por propiedades autoimplementadas.  
  
-   Cada estudiante de la lista se inicializa con un inicializador de objeto.  
  
-   La propia lista se inicializa con un inicializador de colección.  
  
 Esta estructura de datos completa se inicializará, y se crearán instancias de ella, sin llamadas explícitas a un constructor o sin acceso a miembros explícito.  Para obtener más información acerca de estas nuevas características, vea [Propiedades autoimplementadas](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) y [Inicializadores de objeto y colección](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
#### Para agregar el origen de datos  
  
-   Agregue la clase `Student` y la lista inicializada de estudiantes a la clase `Program` de su proyecto.  
  
     [!code-cs[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]  
  
#### Para agregar un nuevo estudiante a la lista de estudiantes  
  
1.  Agregue un nuevo `Student` a la lista `Students` y utilice el nombre y las puntuaciones de examen que desee.  Intente escribir toda la información del nuevo estudiante para aprender mejor la sintaxis del inicializador de objeto.  
  
## Crear la consulta  
  
#### Para crear una consulta sencilla  
  
-   En el método `Main` de la aplicación, cree una consulta simple que, cuando se ejecute, genere una lista de todos los estudiantes cuya puntuación fue mayor que 90 en el primer examen.  Tenga en cuenta que, como se selecciona el objeto `Student`, el tipo de la consulta es `IEnumerable<Student>`.  Aunque en el código también se podría utilizar un tipo implícito mediante la palabra clave [var](../../../../csharp/language-reference/keywords/var.md), se usa un tipo explícito para ilustrar los resultados de forma más clara.  \(Para obtener más información acerca de `var`, vea [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).\)  
  
     Observe también que la variable de rango de la consulta, `student`, sirve de referencia para cada `Student` del origen, proporcionando acceso a los miembros de cada objeto.  
  
 [!code-cs[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]  
  
## Ejecutar la consulta  
  
#### Para ejecutar la consulta  
  
1.  Ahora escriba el bucle `foreach` que hará que se ejecute la consulta.  Tenga en cuenta lo siguiente acerca del código:  
  
    -   Se tiene acceso a cada elemento de la secuencia devuelta a través de la variable de iteración del bucle `foreach`.  
  
    -   El tipo de esta variable es `Student`, y el tipo de la variable de consulta es compatible, `IEnumerable<Student>`.  
  
2.  Después de haber agregado este código, compile y ejecute la aplicación; para ello, presione Ctrl \+ F5. Los resultados aparecerán en la ventana **Consola**.  
  
 [!code-cs[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]  
  
#### Para agregar otra condición de filtro  
  
1.  Puede combinar varias condiciones booleanas en la cláusula `where` para delimitar más la consulta.  El código siguiente agrega una condición para que la consulta devuelva los estudiantes cuya primera puntuación fue superior a 90 y cuya última puntuación fue inferior a 80.  La cláusula `where` se debería parecer a la del código siguiente.  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     Para obtener más información, consulte [where \(cláusula\)](../../../../csharp/language-reference/keywords/where-clause.md).  
  
## Modificar la consulta  
  
#### Para ordenar los resultados  
  
1.  Será más fácil examinar los resultados si están ordenados de alguna manera.  Puede ordenar la secuencia devuelta según cualquier campo accesible de los elementos de origen.  Por ejemplo, la cláusula `orderby` siguiente ordena los resultados alfabéticamente, de la A a la Z, por apellido de estudiante.  Agregue la siguiente cláusula `orderby` a la consulta, justo detrás de la instrucción `where` y delante de la instrucción `select`:  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  Ahora cambie la cláusula `orderby` de forma que ordene los resultados en orden inverso, según la puntuación del primer examen, de mayor a menor.  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  Cambie la cadena de formato `WriteLine` para poder ver las puntuaciones:  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     Para obtener más información, consulte [orderby \(cláusula\)](../../../../csharp/language-reference/keywords/orderby-clause.md).  
  
#### Para agrupar los resultados  
  
1.  La agrupación es una funcionalidad eficaz para las expresiones de consulta.  Una consulta con una cláusula group genera una secuencia de grupos donde cada grupo contiene una `Key` y una secuencia compuesta por todos los miembros de ese grupo.  La siguiente consulta nueva agrupa los estudiantes utilizando como clave la inicial de su apellido.  
  
     [!code-cs[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]  
  
2.  Observe que el tipo de la consulta ha cambiado.  Ahora genera una secuencia de grupos que tienen un tipo `char` como clave y una secuencia de objetos `Student`.  Dado que el tipo de la consulta ha cambiado, el código siguiente también cambia el bucle de ejecución `foreach`:  
  
     [!code-cs[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]  
  
3.  Presione Ctrl \+ F5 para ejecutar la aplicación y ver los resultados en la ventana **Consola**.  
  
     Para obtener más información, consulte [group \(cláusula\)](../../../../csharp/language-reference/keywords/group-clause.md).  
  
#### Para hacer que las variables sean de tipo implícito  
  
1.  Codificar explícitamente `IEnumerables` de `IGroupings` se puede convertir pronto en una tarea complicada.  Puede escribir la misma consulta y el mismo bucle `foreach` de una forma mucho más sencilla utilizando `var`.  La palabra clave `var` no cambia los tipos de los objetos; simplemente indica al compilador que los deduzca.  Cambie el tipo de `studentQuery` y la iteración `group` variable a `var` y vuelva a ejecutar la consulta.  Observe que en el bucle `foreach` interno, la variable de iteración todavía es de tipo `Student` y la consulta funciona igual que antes.  Cambie la variable de iteración `s` a `var` y ejecute de nuevo la consulta.  Verá que obtiene exactamente los mismos resultados.  
  
     [!code-cs[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]  
  
     Para obtener más información acerca de [var](../../../../csharp/language-reference/keywords/var.md), vea [Variables locales con asignación implícita de tipos](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
#### Para ordenar los grupos por su valor de clave  
  
1.  Al ejecutar la consulta anterior, verá que los grupos no están ordenados alfabéticamente.  Para cambiar esto, debe proporcionar una cláusula `orderby` después de la cláusula `group`.  Sin embargo, para usar una cláusula `orderby`, primero necesita un identificador que sirva de referencia para los grupos creados por la cláusula `group`.  Proporcione el identificador utilizando la palabra clave `into`, como se indica a continuación:  
  
     [!code-cs[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]  
  
     Al ejecutar esta consulta, verá que ahora los grupos están ordenados alfabéticamente.  
  
#### Incluir un identificador mediante let  
  
1.  Puede utilizar la palabra clave `let` para incluir un identificador para cualquier resultado de expresión de la expresión de consulta.  Este identificador puede usarse por comodidad, como en el ejemplo siguiente, o para mejorar el rendimiento, ya que almacena los resultados de una expresión para que no tenga que calcularse varias veces.  
  
     [!code-cs[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]  
  
     Para obtener más información, consulte [let \(cláusula\)](../../../../csharp/language-reference/keywords/let-clause.md).  
  
#### Para utilizar la sintaxis de método en una expresión de consulta  
  
1.  Como se describe en [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md), algunas operaciones de consulta sólo se pueden expresar utilizando sintaxis de método.  El código siguiente calcula la puntuación total de cada `Student` de la secuencia de origen y, después, llama al método `Average()` en los resultados de esa consulta para calcular la puntuación promedio de la clase.  Observe la posición de los paréntesis alrededor de la expresión de consulta.  
  
     [!code-cs[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]  
  
#### Para transformar o proyectar en la cláusula select  
  
1.  Es muy común que una consulta genere una secuencia cuyos elementos difieren de los elementos de las secuencias de origen.  Elimine o marque como comentario la consulta y el bucle de ejecución anteriores y reemplácelos con el código siguiente.  Observe que la consulta devuelve una secuencia de cadenas \(no `Students`\) y este hecho se refleja en el bucle `foreach`.  
  
     [!code-cs[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]  
  
2.  El código anterior de este tutorial indicaba que la puntuación media de la clase es de 334, aproximadamente.  Para generar una secuencia de `Students` cuya puntuación total sea mayor que la media de la clase, junto con su `Student ID`, puede usar un tipo anónimo en la instrucción `select`:  
  
     [!code-cs[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]  
  
## Pasos siguientes  
 Una vez que esté familiarizado con los aspectos básicos del uso de consultas in C\#, estará preparado para leer la documentación y ver los ejemplos del tipo de proveedor [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] específico que le interese:  
  
 [LINQ a SQL](../Topic/LINQ%20to%20SQL.md)  
  
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
## Vea también  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Supplementary LINQ Resources](../Topic/Supplementary%20LINQ%20Resources.md)   
 [Tutorial: Escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)