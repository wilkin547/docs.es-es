---
title: 'Tutorial: Escribir consultas en C# (LINQ)'
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: f2135c6c3649ba2fc87e3b49770439688a58269b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73418055"
---
# <a name="walkthrough-writing-queries-in-c-linq"></a>Tutorial: Escribir consultas en C# (LINQ)
Este tutorial muestra las características del lenguaje C# que se usan para escribir expresiones de consulta de LINQ.  
  
## <a name="create-a-c-project"></a>Crear un proyecto de C#  
  
> [!NOTE]
> Las siguientes instrucciones se aplican a Visual Studio. Si usa otro entorno de desarrollo, cree un proyecto de consola con una referencia a System.Core.dll y una directiva `using` para el espacio de nombres <xref:System.Linq?displayProperty=nameWithType>.  
  
#### <a name="to-create-a-project-in-visual-studio"></a>Para crear un proyecto en Visual Studio  
  
1. Inicie Visual Studio.  
  
2. En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto** .  
  
3. Expanda **Instalado**, **Plantillas**, **Visual C#** y luego elija **Aplicación de consola**.  
  
4. En el cuadro de texto **Nombre**, escriba otro nombre o acepte el predeterminado y luego elija el botón **Aceptar**.  
  
     El nuevo proyecto aparece en el **Explorador de soluciones**.  
  
5. Observe que el proyecto tiene una referencia a System.Core.dll y una directiva `using` para el espacio de nombres <xref:System.Linq?displayProperty=nameWithType>.  
  
## <a name="create-an-in-memory-data-source"></a>Crear un origen de datos en memoria  
 El origen de datos de las consultas es una simple lista de objetos `Student`. Cada registro `Student` tiene un nombre, un apellido y una matriz de enteros que representa sus puntuaciones de las pruebas en la clase. Copie este código en el proyecto. Observe las siguientes características:  
  
- La clase `Student` consta de propiedades implementadas automáticamente.  
  
- Cada alumno de la lista se inicializa con un inicializador de objeto.  
  
- La propia lista se inicializa con un inicializador de colección.  
  
 Toda la estructura de datos se inicializará y creará una instancia sin llamadas explícitas a ningún constructor ni acceso a miembro explícito. Para obtener más información sobre estas nuevas características, vea [Propiedades autoimplementadas](../../classes-and-structs/auto-implemented-properties.md) (Propiedades implementadas automáticamente) y [Inicializadores de objeto y de colección](../../classes-and-structs/object-and-collection-initializers.md).  
  
#### <a name="to-add-the-data-source"></a>Para agregar el origen de datos  
  
- Agregue la clase `Student` y la lista inicializada de alumnos a la clase `Program` del proyecto.  
  
     [!code-csharp[CsLinqGettingStarted#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#11)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Para agregar un nuevo alumno a la lista de alumnos  
  
1. Agregue un nuevo `Student` a la lista `Students` y use el nombre y las puntuaciones de las pruebas que prefiera. Pruebe a escribir toda la nueva información de alumno para conocer mejor la sintaxis del inicializador de objeto.  
  
## <a name="create-the-query"></a>Crear la consulta  
  
#### <a name="to-create-a-simple-query"></a>Para crear una consulta simple  
  
- En el método `Main` de la aplicación, cree una consulta simple que, cuando se ejecute, genere una lista de todos los alumnos cuya puntuación en la primera prueba haya sido superior a 90. Tenga en cuenta que, dado que se ha seleccionado todo el objeto `Student`, el tipo de la consulta es `IEnumerable<Student>`. Aunque el código podría usar tipos implícitos con la palabra clave [var](../../../language-reference/keywords/var.md), se usan tipos explícitos para mostrar claramente los resultados. (Para obtener más información sobre `var`, vea [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md) [Variables locales con tipo implícito]).  
  
     Tenga también en cuenta que la variable de rango de la consulta, `student`, actúa como referencia a cada `Student` del origen, lo que proporciona acceso a miembro para cada objeto.  
  
 [!code-csharp[CsLINQGettingStarted#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#12)]  
  
## <a name="execute-the-query"></a>Ejecutar la consulta  
  
#### <a name="to-execute-the-query"></a>Para ejecutar la consulta  
  
1. Escriba ahora el bucle `foreach` que hará que la consulta se ejecute. Tenga en cuenta los siguiente sobre el código:  
  
    - A cada elemento de la secuencia devuelta se accede mediante la variable de iteración del bucle `foreach`.  
  
    - El tipo de esta variables es `Student` y el tipo de la variable de consulta es compatible, `IEnumerable<Student>`.  
  
2. Tras agregar este código, compile y ejecute la aplicación para ver los resultados en la ventana **Consola**.  
  
 [!code-csharp[CsLINQGettingStarted#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#13)]  
  
#### <a name="to-add-another-filter-condition"></a>Para agregar otra condición de filtro  
  
1. Puede combinar varias condiciones booleanas en la cláusula `where` para delimitar aún más una consulta. El código siguiente agrega una condición para que la consulta devuelva los alumnos cuya primera puntuación haya sido superior a 90 y cuya última puntuación haya sido inferior a 80. La cláusula `where` debería ser similar al código siguiente.  
  
    ```csharp
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     Para obtener más información, vea [where (Cláusula)](../../../language-reference/keywords/where-clause.md).  
  
## <a name="modify-the-query"></a>Modificar la consulta  
  
#### <a name="to-order-the-results"></a>Para ordenar los resultados  
  
1. Le resultará más fácil examinar los resultados si se muestran con algún tipo de orden. Puede ordenar la secuencia devuelta por cualquier campo accesible de los elementos de origen. Por ejemplo, la cláusula `orderby` siguiente ordena los resultados alfabéticamente de la A a la Z por el apellido de cada alumno. Agregue la cláusula `orderby` siguiente a la consulta, inmediatamente después de la instrucción `where` y antes de la instrucción `select`:  
  
    ```csharp
    orderby student.Last ascending  
    ```  
  
2. Cambie ahora la cláusula `orderby` para que ordene los resultados en orden inverso según la puntuación en la primera prueba, de la puntuación más alta a la más baja.  
  
    ```csharp
    orderby student.Scores[0] descending  
    ```  
  
3. Cambie la cadena de formato `WriteLine` para poder ver las puntuaciones:  
  
    ```csharp
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     Para obtener más información, vea [orderby (Cláusula)](../../../language-reference/keywords/orderby-clause.md).  
  
#### <a name="to-group-the-results"></a>Para agrupar los resultados  
  
1. La agrupación es una funcionalidad de gran eficacia en expresiones de consulta. Una consulta con una cláusula group genera una secuencia de grupos y cada grupo propiamente dicho contiene un `Key` y una secuencia que consta de todos los miembros del grupo. La siguiente nueva consulta agrupa los alumnos usando la primera letra del apellido como clave.  
  
     [!code-csharp[CsLINQGettingStarted#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#14)]  
  
2. Tenga en cuenta que el tipo de la consulta ha cambiado. Ahora genera una secuencia de grupos que tienen un tipo `char` como clave y una secuencia de objetos `Student`. Dado que el tipo de la consulta ha cambiado, el siguiente código cambia también el bucle de ejecución `foreach`:  
  
     [!code-csharp[CsLINQGettingStarted#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#15)]  
  
3. Ejecute la aplicación y vea los resultados en la ventana **Consola**.  
  
     Para obtener más información, vea [group (Cláusula)](../../../language-reference/keywords/group-clause.md).  
  
#### <a name="to-make-the-variables-implicitly-typed"></a>Para que las variables tengan tipo implícito  
  
1. La codificación explícita con `IEnumerables` de `IGroupings` puede resultar tediosa. Puede escribir la misma consulta y el bucle `foreach` mucho más cómodamente con `var`. La palabra clave `var` no cambia los tipos de los objetos; solo indica al compilador que deduzca los tipos. Cambie el tipo de `studentQuery` y la variable de iteración `group` a `var` y vuelva a ejecutar la consulta. Tenga en cuenta que en el bucle `foreach` interior, la variable de iteración sigue teniendo como tipo `Student` y la consulta funciona igual que antes. Cambie la variable de iteración `s` a `var` y vuelva a ejecutar la consulta. Como puede ver, obtiene exactamente los mismos resultados.  
  
     [!code-csharp[CsLINQGettingStarted#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#16)]  
  
     Para obtener más información sobre [var](../../../language-reference/keywords/var.md), vea [Variables locales con asignación implícita de tipos](../../classes-and-structs/implicitly-typed-local-variables.md).  
  
#### <a name="to-order-the-groups-by-their-key-value"></a>Para ordenar los grupos por su valor clave  
  
1. Al ejecutar la consulta anterior, observará que los grupos no están en orden alfabético. Para cambiar esto, debe especificar una cláusula `orderby` después de la cláusula `group`. Pero para usar una cláusula `orderby`, necesita primero un identificador que actúe como referencia a los grupos creados por la cláusula `group`. El identificador se especifica con la palabra clave `into`, de la manera siguiente:  
  
     [!code-csharp[csLINQGettingStarted#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#17)]  
  
     Cuando ejecute esta consulta, verá que los grupos aparecen ahora ordenados alfabéticamente.  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a>Para incluir un identificador mediante let  
  
1. Puede usar la palabra clave `let` para incluir un identificador con cualquier resultado de la expresión en la expresión de consulta. Este identificador puede resultar cómodo, como en el ejemplo siguiente, o mejorar el rendimiento almacenando los resultados de una expresión para que no tenga que calcularse varias veces.  
  
     [!code-csharp[csLINQGettingStarted#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#18)]  
  
     Para obtener más información, vea [let (Cláusula)](../../../language-reference/keywords/let-clause.md).  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a>Para usar la sintaxis de método en una expresión de consulta  
  
1. Tal y como se describe en [Sintaxis de consulta y sintaxis de método en LINQ](./query-syntax-and-method-syntax-in-linq.md), algunas operaciones de consulta solo pueden expresarse con una sintaxis de método. El código siguiente calcula la puntuación total de cada `Student` de la secuencia de origen y luego llama al método `Average()` en los resultados de esa consulta para calcular la puntuación media de la clase.
  
     [!code-csharp[csLINQGettingStarted#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#19)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a>Para transformar o proyectar en la cláusula select  
  
1. Es muy frecuente que una consulta genere una secuencia cuyos elementos difieren de los elementos de las secuencias de origen. Elimine la consulta y el bucle de ejecución anteriores o conviértalos en comentario, y reemplácelos por el código siguiente. Tenga en cuenta que la consulta devuelve una secuencia de cadenas (no `Students`) y este hecho se refleja en el bucle `foreach`.  
  
     [!code-csharp[csLINQGettingStarted#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#20)]  
  
2. El código anterior en este tutorial indicaba que la puntuación media de la clase es aproximadamente 334. Para generar una secuencia de `Students` cuya puntuación total sea superior al promedio de la clase, junto con su `Student ID`, puede usar un tipo anónimo en la instrucción `select`:  
  
     [!code-csharp[csLINQGettingStarted#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#21)]  
  
## <a name="next-steps"></a>Pasos siguientes  
 Cuando se haya familiarizado con los aspectos básicos del uso de consultas en C#, estará preparado para leer la documentación y ejemplos del tipo específico de proveedor LINQ que le interese:  
  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [LINQ to XML (C#)](./linq-to-xml-overview.md)  
  
 [LINQ to Objects (C#)](./linq-to-objects.md)  
  
## <a name="see-also"></a>Vea también

- [Language Integrated Query (LINQ) (C#)](./index.md)
- [Expresiones de consulta LINQ](../../../linq/index.md)
