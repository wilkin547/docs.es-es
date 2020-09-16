---
title: Creación de consultas
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: c2abca183f1241cff314a4367c7bd9f1b9f239ea
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554598"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Tutorial: Escribir consultas en Visual Basic

En este tutorial se muestra cómo puede usar las características del lenguaje Visual Basic para escribir expresiones de consulta de Language-Integrated Query (LINQ). En el tutorial se muestra cómo crear consultas en una lista de objetos de estudiante, cómo ejecutar las consultas y cómo modificarlas. Las consultas incorporan varias características, como inicializadores de objeto, inferencia de tipo local y tipos anónimos.

Después de completar este tutorial, estará listo para pasar a los ejemplos y la documentación del proveedor LINQ específico que le interese. Los proveedores LINQ incluyen [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] , LINQ to DataSet y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .

## <a name="create-a-project"></a>Crear un proyecto

### <a name="to-create-a-console-application-project"></a>Para crear un proyecto de aplicación de consola

1. Inicie Visual Studio.

2. En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.

3. En la lista **plantillas instaladas** , haga clic en **Visual Basic**.

4. En la lista de tipos de proyecto, haga clic en **aplicación de consola**. En el cuadro **nombre** , escriba un nombre para el proyecto y, a continuación, haga clic en **Aceptar**.

    Se crea un proyecto. De forma predeterminada, contiene una referencia a System.Core.dll. Además, la lista de **espacios de nombres importados** en la [Página referencias, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) incluye el <xref:System.Linq?displayProperty=nameWithType> espacio de nombres.

5. En la [Página compilar, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que la **opción Infer** está establecida en **on**.

## <a name="add-an-in-memory-data-source"></a>Agregar un origen de datos en memoria

El origen de datos para las consultas de este tutorial es una lista de `Student` objetos. Cada `Student` objeto contiene un nombre, un apellido, un año de clase y un rango académico en el cuerpo del alumno.

### <a name="to-add-the-data-source"></a>Para agregar el origen de datos

- Defina una `Student` clase y cree una lista de instancias de la clase.

  > [!IMPORTANT]
  > El código necesario para definir la `Student` clase y crear la lista que se usa en los ejemplos del tutorial se proporciona en [Cómo: crear una lista de elementos](how-to-create-a-list-of-items.md). Puede copiarlo desde allí y pegarlo en el proyecto. El nuevo código reemplaza el código que aparecía al crear el proyecto.

### <a name="to-add-a-new-student-to-the-students-list"></a>Para agregar un estudiante nuevo a la lista de estudiantes

- Siga el patrón del `getStudents` método para agregar otra instancia de la `Student` clase a la lista. Agregar el estudiante le presentará los inicializadores de objeto. Para obtener más información, vea [inicializadores de objeto: tipos con nombre y anónimos](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).

## <a name="create-a-query"></a>Crear una consulta

Cuando se ejecuta, la consulta agregada en esta sección genera una lista de los estudiantes cuyo rango académico los coloca en los diez principales. Dado que la consulta selecciona el `Student` objeto completo cada vez, el tipo del resultado de la consulta es `IEnumerable(Of Student)` . Sin embargo, el tipo de la consulta no se especifica normalmente en las definiciones de consulta. En su lugar, el compilador usa la inferencia de tipo local para determinar el tipo. Para obtener más información, vea [inferencia de tipo local](../../language-features/variables/local-type-inference.md). La variable de rango de la consulta, `currentStudent` , sirve como referencia a cada `Student` instancia en el origen, `students` y proporciona acceso a las propiedades de cada objeto en `students` .

### <a name="to-create-a-simple-query"></a>Para crear una consulta simple

1. Busque el lugar en el `Main` método del proyecto que se marca como sigue:

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    Copie el código siguiente y péguelo en.

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. Sitúe el puntero del mouse sobre `studentQuery` el código para comprobar que el tipo asignado por el compilador es `IEnumerable(Of Student)` .

## <a name="run-the-query"></a>Ejecutar la consulta

La variable `studentQuery` contiene la definición de la consulta, no los resultados de la ejecución de la consulta. Un mecanismo típico para ejecutar una consulta es un `For Each` bucle. Se tiene acceso a cada elemento de la secuencia devuelta a través de la variable de iteración del bucle. Para obtener más información sobre la ejecución de consultas, vea [escribir su primera consulta LINQ](writing-your-first-linq-query.md).

### <a name="to-run-the-query"></a>Para ejecutar la consulta

1. Agregue el siguiente `For Each` bucle debajo de la consulta en el proyecto.

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. Sitúe el puntero del mouse sobre la variable `studentRecord` de control de bucle para ver su tipo de datos. El tipo de `studentRecord` se deduce como `Student` , porque `studentQuery` devuelve una colección de `Student` instancias de.

3. Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de la consola.

## <a name="modify-the-query"></a>Modificar la consulta

Es más fácil analizar los resultados de la consulta si están en un orden especificado. Puede ordenar la secuencia devuelta según cualquier campo disponible.

### <a name="to-order-the-results"></a>Para ordenar los resultados

1. Agregue la siguiente `Order By` cláusula entre la `Where` instrucción y la `Select` instrucción de la consulta. La `Order By` cláusula ordenará los resultados alfabéticamente de la a a la Z, según el apellido de cada estudiante.

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. Para ordenar por Apellido y luego por nombre, agregue ambos campos a la consulta:

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    También puede especificar `Descending` para ordenar de Z A a.

3. Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de la consola.

### <a name="to-introduce-a-local-identifier"></a>Para introducir un identificador local

1. Agregue el código de esta sección para introducir un identificador local en la expresión de consulta. El identificador local contendrá un resultado intermedio. En el ejemplo siguiente, `name` es un identificador que contiene una concatenación del nombre y los apellidos del estudiante. Un identificador local se puede usar para mayor comodidad, o puede mejorar el rendimiento almacenando los resultados de una expresión que de otro modo se calcularía varias veces.

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de la consola.

### <a name="to-project-one-field-in-the-select-clause"></a>Para proyectar un campo en la cláusula SELECT

1. Agregue la consulta y el `For Each` bucle desde esta sección para crear una consulta que genere una secuencia cuyos elementos difieren de los elementos del origen. En el ejemplo siguiente, el origen es una colección de `Student` objetos, pero solo se devuelve un miembro de cada objeto: el nombre de los estudiantes cuyo apellido es Garcia. Dado que `currentStudent.First` es una cadena, el tipo de datos de la secuencia devuelta por `studentQuery3` es `IEnumerable(Of String)` , una secuencia de cadenas. Como en los ejemplos anteriores, la asignación de un tipo de datos de `studentQuery3` se deja para que el compilador determine mediante la inferencia de tipo de variable local.

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. Sitúe el puntero del mouse sobre `studentQuery3` el código para comprobar que el tipo asignado es `IEnumerable(Of String)` .

3. Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de la consola.

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Para crear un tipo anónimo en la cláusula SELECT

1. Agregue el código de esta sección para ver cómo se usan los tipos anónimos en las consultas. Se usan en consultas cuando se desea devolver varios campos del origen de datos en lugar de registros completos ( `currentStudent` registros en ejemplos anteriores) o campos individuales ( `First` en la sección anterior). En lugar de definir un nuevo tipo con nombre que contenga los campos que desea incluir en el resultado, especifique los campos en la `Select` cláusula y el compilador creará un tipo anónimo con esos campos como sus propiedades. Para obtener más información, consulte [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md) (Guía de programación de C#).

    En el ejemplo siguiente se crea una consulta que devuelve el nombre y el rango de los directivos cuyo rango académico está entre 1 y 10, en el orden de los rangos académicos. En este ejemplo, el tipo de `studentQuery4` se debe inferir porque la `Select` cláusula devuelve una instancia de un tipo anónimo y un tipo anónimo no tiene ningún nombre utilizable.

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de la consola.

## <a name="additional-examples"></a>Otros ejemplos

Ahora que comprende los conceptos básicos, a continuación se muestra una lista de ejemplos adicionales para ilustrar la flexibilidad y la eficacia de las consultas de LINQ. Cada ejemplo va precedido de una breve descripción de lo que hace. Sitúe el puntero del mouse sobre la variable de resultado de la consulta para cada consulta para ver el tipo deducido. Use un `For Each` bucle para generar los resultados.

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a>Información adicional

Una vez que esté familiarizado con los conceptos básicos sobre cómo trabajar con consultas, está listo para leer la documentación y los ejemplos del tipo específico de proveedor LINQ que le interesa:

- [LINQ to Objects](linq-to-objects.md)

- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)

- [LINQ to XML](../../../../standard/linq/linq-xml-overview.md)

- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ) (Visual Basic)](index.md)
- [Introducción a LINQ en Visual Basic](getting-started-with-linq.md)
- [Inferencia de tipo de variable local](../../language-features/variables/local-type-inference.md)
- [Inicializadores de objeto: tipos con nombre y anónimos](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md)
- [Introducción a LINQ en Visual Basic](../../language-features/linq/introduction-to-linq.md)
- [LINQ](../../language-features/linq/index.md)
- [Consultas](../../../language-reference/queries/index.md)
