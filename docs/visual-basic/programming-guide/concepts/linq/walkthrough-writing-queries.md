---
title: "Tutorial: Escribir consultas en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [LINQ en Visual Basic], escritura"
  - "LINQ [Visual Basic], tutoriales"
  - "LINQ [Visual Basic], escritura de consultas"
  - "escribir consultas de LINQ [Visual Basic]"
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: 70
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 68
---
# Tutorial: Escribir consultas en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este tutorial muestra cómo se pueden utilizar las características del lenguaje Visual Basic para escribir expresiones de consulta [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)].  El tutorial muestra cómo crear consultas en una lista de objetos Student, cómo ejecutar las consultas y cómo modificarlas.  Las consultas incorporan varias características nuevas de Visual Basic 2008, incluidos los inicializadores de objeto, la inferencia de tipos de variable local y los tipos anónimos.  
  
 Después de completar este tutorial, estará preparado para ver los ejemplos y la documentación del proveedor [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] específico que le interese.  Entre los proveedores [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] se incluyen [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/linq-query-expressions/includes/linq-dataset-md.md)] y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  
  
## Crear un proyecto  
  
#### Para crear un proyecto de aplicación de consola  
  
1.  Inicie Visual Studio.  
  
2.  En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto**.  
  
3.  En la lista **Plantillas instaladas**, haga clic en **Visual Basic**.  
  
4.  En la lista de tipos de proyecto, haga clic en **Aplicación de consola**.  En el cuadro **Nombre**, escriba un nombre para el proyecto y, a continuación, haga clic en **Aceptar**.  
  
     Se crea un proyecto.  De forma predeterminada, contiene una referencia a System.Core.dll.  Asimismo, la lista **Espacios de nombres importados** de [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic) incluye el espacio de nombres <xref:System.Linq?displayProperty=fullName>.  
  
5.  En [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que **Option Infer** está establecido en **En**.  
  
## Agregar un origen de datos en memoria  
 El origen de datos de las consultas de este tutorial es una lista de objetos `Student`.  Cada objeto `Student` contiene un nombre, un apellido, un año de clase y un grado académico en el cuerpo del estudiante.  
  
#### Para agregar el origen de datos  
  
-   Defina una clase `Student` y cree una lista de instancias de la clase.  
  
    > [!IMPORTANT]
    >  El código necesario para definir la clase `Student` y crear la lista que se utiliza en los ejemplos del tutorial se proporciona en [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  Puede copiarlo de allí y pegarlo en su proyecto.  El nuevo código reemplaza el código que aparecía al crear el proyecto.  
  
#### Para agregar un nuevo estudiante a la lista de estudiantes  
  
-   Siga el modelo del método `getStudents` para agregar otra instancia de la clase `Student` a la lista.  Al agregar el estudiante, verá por primera vez los inicializadores de objeto.  Para obtener más información, vea [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## Crear una consulta  
 Cuando se ejecute, la consulta agregada en esta sección generará una lista de los estudiantes cuyo grado académico los sitúa entre los diez mejores.  Dado que la consulta selecciona cada vez el objeto `Student` completo, el tipo del resultado de la consulta es `IEnumerable(Of Student)`.  Sin embargo, el tipo de la consulta no suele especificarse en las definiciones de consulta.  En su lugar, el compilador utiliza la inferencia de tipo de variable local para determinar el tipo.  Para obtener más información, vea [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  La variable de rango de la consulta, `currentStudent`, actúa como referencia para cada instancia de `Student` del origen, `students`, proporcionando acceso a las propiedades de cada objeto de `students`.  
  
#### Para crear una consulta sencilla  
  
1.  Busque la parte del método `Main` del proyecto que está marcada de esta manera:  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_1.vb)]  
  
     Copie el código siguiente y péguelo en ella.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_2.vb)]  
  
2.  Sitúe el puntero del mouse encima de `studentQuery` en el código para comprobar que el tipo asignado por el compilador es `IEnumerable(Of Student)`.  
  
## Ejecutar la consulta  
 La variable `studentQuery` contiene la definición de la consulta, no los resultados de ejecutarla.  Un mecanismo habitual para ejecutar una consulta es un bucle `For Each`.  Se tiene acceso a cada elemento de la secuencia devuelta a través de la variable de iteración del bucle.  Para obtener más información sobre la ejecución de consultas, vea [Escribir la primera consulta con LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### Para ejecutar la consulta  
  
1.  Agregue el bucle `For Each` siguiente debajo de la consulta en su proyecto.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_3.vb)]  
  
2.  Sitúe el puntero del mouse encima de la variable de control de bucle `studentRecord` para ver su tipo de datos.  Se infiere que el tipo de `studentRecord` es `Student`, porque `studentQuery` devuelve una colección de instancias de `Student`.  
  
3.  Compile y ejecute la aplicación; para ello, presione CTRL\+F5.  Observe los resultados en la ventana de la consola.  
  
## Modificar la consulta  
 Es más fácil examinar los resultados de la consulta si están en un orden concreto.  Puede ordenar la secuencia devuelta según cualquier campo que esté disponible.  
  
#### Para ordenar los resultados  
  
1.  Agregue la cláusula `Order By` siguiente entre la instrucción `Where` y la instrucción `Select` de la consulta.  La cláusula `Order By` ordenará los resultados alfabéticamente de la A a la Z, por apellido de estudiante.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Para ordenar los resultados primero por apellido y después por nombre, agregue ambos campos a la consulta:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     También puede especificar `Descending` para ordenar los resultados de la Z a la A.  
  
3.  Compile y ejecute la aplicación; para ello, presione CTRL\+F5.  Observe los resultados en la ventana de la consola.  
  
#### Para incluir un identificador local  
  
1.  Agregue el código de esta sección para incluir un identificador local en la expresión de consulta.  El identificador local contendrá un resultado intermedio.  En el ejemplo siguiente, `name` es un identificador que contiene una concatenación del nombre y el apellido del estudiante.  Se puede usar un identificador local por comodidad o para mejorar el rendimiento, ya que almacena los resultados de una expresión que, de otro modo, se calcularía varias veces.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_4.vb)]  
  
2.  Compile y ejecute la aplicación; para ello, presione CTRL\+F5.  Observe los resultados en la ventana de la consola.  
  
#### Para proyectar un campo en la cláusula Select  
  
1.  Agregue la consulta y el bucle `For Each` de esta sección para crear una consulta que genere una secuencia cuyos elementos difieran de los elementos del origen.  En el ejemplo siguiente, el origen es una colección de objetos `Student`, pero sólo se devuelve un único miembro de cada objeto: el nombre de los estudiantes cuyo apellido es García.  Dado que `currentStudent.First` es una cadena, el tipo de datos de la secuencia devuelta por `studentQuery3` es `IEnumerable(Of String)`, una secuencia de cadenas.  Como en ejemplos anteriores, la asignación del tipo de datos de `studentQuery3` se deja en manos del compilador, que lo determinará mediante la inferencia de tipo de variable local.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_5.vb)]  
  
2.  Sitúe el puntero del mouse encima de `studentQuery3` en el código para comprobar que el tipo asignado es `IEnumerable(Of String)`.  
  
3.  Compile y ejecute la aplicación; para ello, presione CTRL\+F5.  Observe los resultados en la ventana de la consola.  
  
#### Para crear un tipo anónimo en la cláusula Select  
  
1.  Agregue el código de esta sección para ver cómo se utilizan los tipos anónimos en las consultas.  Se utilizan en las consultas cuando se desea devolver varios campos del origen de datos en lugar de registros completos \(registros `currentStudent` en los ejemplos anteriores\) o campos únicos \(`First` en la sección anterior\).  En lugar de definir un nuevo tipo con nombre que contenga los campos que desea incluir en el resultado, los campos se especifican en la cláusula de `Select` y el compilador crea un tipo anónimo con esos campos como sus propiedades. Para obtener más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     En el ejemplo siguiente se crea una consulta que devuelve el nombre y la condición de estudiante matriculado en el último año de estudios \(senior\) cuyo grado académico esté entre 1 y 10, por orden de grado académico.  En este ejemplo, el tipo de `studentQuery4` se debe deducir, porque la cláusula `Select` devuelve una instancia de tipo anónimo, y un tipo anónimo no tiene ningún nombre utilizable.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_6.vb)]  
  
2.  Compile y ejecute la aplicación; para ello, presione CTRL\+F5.  Observe los resultados en la ventana de la consola.  
  
## Ejemplos adicionales  
 Ahora que ya comprende los conceptos básicos, aquí tiene una lista de ejemplos adicionales que ilustran la flexibilidad y eficacia de las consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Cada ejemplo va precedido de una breve descripción de lo que hace.  Sitúe el puntero del mouse sobre la variable de resultado de cada consulta para ver el tipo deducido. Utilice un bucle de `For Each` para generar los resultados.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/visualbasic/walkthrough-writing-quer_1_7.vb)]  
  
## Información adicional  
 Una vez que esté familiarizado con los conceptos básicos del uso de consultas, estará preparado para leer la documentación y ver los ejemplos del tipo de proveedor [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] específico que le interese:  
  
 [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
 [LINQ a SQL](../Topic/LINQ%20to%20SQL.md)  
  
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)  
  
## Vea también  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Supplementary LINQ Resources](../Topic/Supplementary%20LINQ%20Resources.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [Walkthrough: Writing Queries in C\#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)