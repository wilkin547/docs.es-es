---
title: Escribir consultas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 2f641d04b53d2e80985defcd6bd9a4882004fd97
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415480"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Tutorial: Escribir consultas en Visual Basic
Este tutorial muestra cómo puede utilizar las características del lenguaje Visual Basic para escribir [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] las expresiones de consulta. El tutorial muestra cómo crear consultas en una lista de objetos Student, cómo ejecutar las consultas y cómo modificarlos. Las consultas incorporan varias características que incluyen tipos anónimos, inferencia de tipos local y los inicializadores de objeto.  
  
 Después de completar este tutorial, estará listo para pasar a los ejemplos y documentación específica para la [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] está interesado en el proveedor. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] incluyen proveedores [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="create-a-project"></a>Crear un proyecto  
  
#### <a name="to-create-a-console-application-project"></a>Para crear un proyecto de aplicación de consola  
  
1.  Inicie Visual Studio.  
  
2.  En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.  
  
3.  En el **plantillas instaladas** lista, haga clic en **Visual Basic**.  
  
4.  En la lista de tipos de proyecto, haga clic en **aplicación de consola**. En el **nombre** , escriba un nombre para el proyecto y, a continuación, haga clic en **Aceptar**.  
  
     Se crea un proyecto. De forma predeterminada, contiene una referencia a System.Core.dll. Además, el **espacios de nombres importados** lista el [página referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) incluye la <xref:System.Linq?displayProperty=nameWithType> espacio de nombres.  
  
5.  En el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que **Option infer** está establecido en **en**.  
  
## <a name="add-an-in-memory-data-source"></a>Agregar un origen de datos en memoria  
 El origen de datos para las consultas en este tutorial es una lista de `Student` objetos. Cada `Student` objeto contiene un nombre, apellido, un año de la clase y un grado académico en el cuerpo del estudiante.  
  
#### <a name="to-add-the-data-source"></a>Para agregar el origen de datos  
  
-   Definir un `Student` clase y crear una lista de instancias de la clase.  
  
    > [!IMPORTANT]
    >  El código necesario para definir el `Student` clase y crear la lista que se usa en el tutorial se proporcionan ejemplos en [Cómo: crear una lista de elementos de](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Puede copiarla desde allí y péguelo en el proyecto. El nuevo código reemplaza el código que aparece al crear el proyecto.  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Para agregar un nuevo alumno a la lista de estudiantes  
  
-   Siga el patrón en el `getStudents` método para agregar otra instancia de la `Student` clase a la lista. Agregar el alumno le presentará los inicializadores de objeto. Para obtener más información, consulte [inicializadores de objeto: tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="create-a-query"></a>Crear una consulta  
 Cuando se ejecuta, la consulta que agregó en esta sección genera una lista de los alumnos cuyo grado académico coloca en los diez primeros. Dado que la consulta selecciona toda `Student` objeto cada vez, el tipo de resultado de la consulta es `IEnumerable(Of Student)`. Sin embargo, el tipo de la consulta normalmente no se especifica en las definiciones de consulta. En su lugar, el compilador usa la inferencia de tipos local para determinar el tipo. Para obtener más información, consulte [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Variable de rango de la consulta, `currentStudent`, actúa como una referencia a cada `Student` instancia en el origen, `students`, que proporciona acceso a las propiedades de cada objeto de `students`.  
  
#### <a name="to-create-a-simple-query"></a>Para crear una consulta simple  
  
1.  Busque el lugar en el `Main` método del proyecto que está marcado como sigue:  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     Copie el código siguiente y péguelo en.  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  Sitúe el puntero del mouse sobre `studentQuery` en el código para comprobar que el tipo asignado por el compilador es `IEnumerable(Of Student)`.  
  
## <a name="run-the-query"></a>Ejecute la consulta  
 La variable `studentQuery` contiene la definición de la consulta, no los resultados de ejecutar la consulta. Un mecanismo típico para ejecutar una consulta es un `For Each` bucle. Cada elemento de la secuencia devuelta se tiene acceso a través de la variable de iteración del bucle. Para obtener más información acerca de la ejecución de consultas, vea [escribir su primera consulta con LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### <a name="to-run-the-query"></a>Para ejecutar la consulta  
  
1.  Agregue las siguientes `For Each` bucle debajo de la consulta en el proyecto.  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  Sitúe el puntero del mouse sobre la variable de control de bucle `studentRecord` para ver su tipo de datos. El tipo de `studentRecord` se infiere para ser `Student`, porque `studentQuery` devuelve una colección de `Student` instancias.  
  
3.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
## <a name="modify-the-query"></a>Modificar la consulta  
 Es más fácil examinar los resultados de la consulta si están en un orden especificado. Puede ordenar la secuencia devuelta según cualquier campo disponible.  
  
#### <a name="to-order-the-results"></a>Para ordenar los resultados  
  
1.  Agregue el siguiente `Order By` cláusula entre el `Where` instrucción y el `Select` instrucción de la consulta. El `Order By` cláusula ordenará los resultados alfabéticamente de la A Z, por el apellido de cada alumno.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Para ordenar por apellido y, a continuación, el nombre, agregue ambos campos a la consulta:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     También puede especificar `Descending` al orden de Z a.  
  
3.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
#### <a name="to-introduce-a-local-identifier"></a>Para incluir un identificador local  
  
1.  Agregue el código de esta sección para incluir un identificador local en la expresión de consulta. El identificador local contendrá un resultado intermedio. En el ejemplo siguiente, `name` es un identificador que contiene una concatenación del alumno de primera y los apellidos. Se puede usar un identificador local para su comodidad, o puede mejorar el rendimiento almacenando los resultados de una expresión que de lo contrario se calcularía varias veces.  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>Para proyectar un campo en la cláusula Select  
  
1.  Agregue la consulta y `For Each` bucle de esta sección para crear una consulta que genera una secuencia cuyos elementos difieren de los elementos en el origen. En el ejemplo siguiente, el origen es una colección de `Student` objetos, pero sólo un miembro de cada objeto se devuelve: el nombre de los alumnos cuyo apellido es García. Dado que `currentStudent.First` es una cadena, el tipo de datos de la secuencia devuelta por `studentQuery3` es `IEnumerable(Of String)`, una secuencia de cadenas. Como se muestra en ejemplos anteriores, la asignación de datos de un tipo para `studentQuery3` se deja para que el compilador determinar mediante el uso de la inferencia de tipo local.  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  Sitúe el puntero del mouse sobre `studentQuery3` en el código para comprobar que el tipo asignado es `IEnumerable(Of String)`.  
  
3.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Para crear un tipo anónimo en la cláusula Select  
  
1.  Agregue el código de esta sección para ver cómo los tipos anónimos se utilizan en consultas. Usar en las consultas cuando desea devolver varios campos desde el origen de datos en lugar de registros completos (`currentStudent` registros en los ejemplos anteriores) o solo los campos (`First` en la sección anterior). En lugar de definir un nuevo tipo con nombre que contiene los campos que van a incluir en el resultado, especifica los campos en el `Select` cláusula y el compilador crea un tipo anónimo con esos campos como sus propiedades. Para más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     El ejemplo siguiente crea una consulta que devuelve el nombre y el rango de ancianos cuyo grado académico esté entre 1 y 10, en orden de grado académico. En este ejemplo, el tipo de `studentQuery4` debe deducir, porque el `Select` cláusula devuelve una instancia de un tipo anónimo, y un tipo anónimo no tiene ningún nombre utilizable.  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
## <a name="additional-examples"></a>Ejemplos adicionales  
 Ahora que comprende los conceptos básicos, la siguiente es una lista de ejemplos adicionales para ilustrar la flexibilidad y eficacia de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] las consultas. Cada ejemplo está precedido por una breve descripción de lo que hace. Sitúe el puntero del mouse sobre la variable de resultado de consulta para cada consulta ver el tipo deducido. Use un `For Each` bucle para generar los resultados.  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>Información adicional  
 Cuando se haya familiarizado con los conceptos básicos del uso de consultas, está listo para leer la documentación y ejemplos para el tipo específico de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] proveedor que está interesado en:  
  
 [LINQ to Objects](https://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a>Vea también  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Consultas](../../../../visual-basic/language-reference/queries/index.md)
