---
title: Escribir consultas en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
caps.latest.revision: 70
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e870d5d0640c68fa57b07986f2bf8268fd5246c9
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Tutorial: Escribir consultas en Visual Basic
Este tutorial muestra cómo puede utilizar las características del lenguaje Visual Basic para escribir [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] expresiones de consulta. El tutorial muestra cómo crear consultas en una lista de objetos Student, cómo ejecutar las consultas y cómo modificarlas. Las consultas incorporan varias características que incluyen tipos anónimos, inferencia de tipo local y los inicializadores de objeto.  
  
 Después de completar este tutorial, estará listo para pasar a los ejemplos y documentación específica para la [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] proveedor que le interese. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]incluyen proveedores [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], [!INCLUDE[linq_dataset](../../../../csharp/programming-guide/concepts/linq/includes/linq_dataset_md.md)], y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
## <a name="create-a-project"></a>Crear un proyecto  
  
#### <a name="to-create-a-console-application-project"></a>Para crear un proyecto de aplicación de consola  
  
1.  Inicie Visual Studio.  
  
2.  En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.  
  
3.  En el **plantillas instaladas** , haga clic **Visual Basic**.  
  
4.  En la lista de tipos de proyecto, haga clic en **aplicación de consola**. En el **nombre** , escriba un nombre para el proyecto y, a continuación, haga clic en **Aceptar**.  
  
     Crea un proyecto. De forma predeterminada, contiene una referencia a System.Core.dll. Además, el **espacios de nombres importados** lista el [página referencias, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) incluye la <xref:System.Linq?displayProperty=fullName>espacio de nombres.</xref:System.Linq?displayProperty=fullName>  
  
5.  En el [página compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que **Option infer** está establecido en **en**.  
  
## <a name="add-an-in-memory-data-source"></a>Agregar un origen de datos en memoria  
 El origen de datos para las consultas en este tutorial es una lista de `Student` objetos. Cada `Student` objeto contiene un nombre, un apellido, un año de clase y un grado académico en el cuerpo del estudiante.  
  
#### <a name="to-add-the-data-source"></a>Para agregar el origen de datos  
  
-   Definir una `Student` clase y crear una lista de instancias de la clase.  
  
    > [!IMPORTANT]
    >  El código necesario para definir la `Student` clase y crear la lista que se usa en el tutorial se proporcionan ejemplos de [Cómo: crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Puede copiar desde allí y pegarlo en su proyecto. El nuevo código reemplaza el código que aparece al crear el proyecto.  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Para agregar un nuevo estudiante a la lista de estudiantes  
  
-   Siga el modelo la `getStudents` método para agregar otra instancia de la `Student` clase a la lista. Agregar el alumno presentará a los inicializadores de objeto. Para obtener más información, consulte [inicializadores de objeto: tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="create-a-query"></a>Crear una consulta  
 Cuando se ejecuta, la consulta agregada en esta sección genera una lista de los estudiantes cuyo grado académico los sitúa entre los diez mejores. Dado que la consulta selecciona toda `Student` objeto cada vez, el tipo de resultado de la consulta es `IEnumerable(Of Student)`. Sin embargo, el tipo de la consulta normalmente no se especifica en las definiciones de consulta. En su lugar, el compilador utiliza la inferencia de tipo local para determinar el tipo. Para obtener más información, consulte [inferencia de tipo Local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). Variable de rango de la consulta, `currentStudent`, actúa como una referencia a cada `Student` instancia en el origen, `students`, que proporciona acceso a las propiedades de cada objeto de `students`.  
  
#### <a name="to-create-a-simple-query"></a>Para crear una consulta simple  
  
1.  Busque el lugar en el `Main` método del proyecto que está marcado como sigue:  
  
     [!code-vb[1 VbLINQWalkthrough](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     Copie el código siguiente y péguelo en ella.  
  
     [!code-vb[VbLINQWalkthrough&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  Sitúe el puntero del mouse sobre `studentQuery` en el código para comprobar que el tipo asignado por el compilador es `IEnumerable(Of Student)`.  
  
## <a name="run-the-query"></a>Ejecutar la consulta  
 La variable `studentQuery` contiene la definición de la consulta, no los resultados de ejecutar la consulta. Un mecanismo habitual para ejecutar una consulta es un `For Each` bucle. Cada elemento de la secuencia devuelta se tiene acceso a través de la variable de iteración del bucle. Para obtener más información acerca de la ejecución de la consulta, vea [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
#### <a name="to-run-the-query"></a>Para ejecutar la consulta  
  
1.  Agregue las siguientes `For Each` bucle debajo de la consulta en el proyecto.  
  
     [!code-vb[VbLINQWalkthrough&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  Sitúe el puntero del mouse sobre la variable de control de bucle `studentRecord` para ver su tipo de datos. El tipo de `studentRecord` se infiere para ser `Student`, porque `studentQuery` devuelve una colección de `Student` instancias.  
  
3.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
## <a name="modify-the-query"></a>Modificar la consulta  
 Es más fácil examinar los resultados de la consulta si están en un orden especificado. Puede ordenar la secuencia devuelta según cualquier campo disponible.  
  
#### <a name="to-order-the-results"></a>Para ordenar los resultados  
  
1.  Agregue el siguiente `Order By` cláusula entre el `Where` instrucción y el `Select` instrucción de la consulta. El `Order By` cláusula ordenará los resultados alfabéticamente de la A la Z, según el nombre de cada estudiante de la última.  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  Para ordenar por apellido y después por nombre, agregue ambos campos a la consulta:  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     También puede especificar `Descending` en orden de Z a.  
  
3.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
#### <a name="to-introduce-a-local-identifier"></a>Para incluir un identificador local  
  
1.  Agregue el código de esta sección para incluir un identificador local en la expresión de consulta. El identificador local contendrá un resultado intermedio. En el ejemplo siguiente, `name` es un identificador que contiene una concatenación del alumno y el apellido. Puede usar un identificador local por comodidad o puede mejorar el rendimiento al almacenar los resultados de una expresión que de lo contrario se calcularía varias veces.  
  
     [!code-vb[VbLINQWalkthrough Nº&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
#### <a name="to-project-one-field-in-the-select-clause"></a>Para proyectar un campo en la cláusula Select  
  
1.  Agregue la consulta y `For Each` bucle de esta sección para crear una consulta que genera una secuencia cuyos elementos difieren de los elementos en el origen. En el ejemplo siguiente, el origen es una colección de `Student` devuelve objetos, pero sólo un miembro de cada objeto: el nombre de los estudiantes cuyo apellido es García. Porque `currentStudent.First` es una cadena, el tipo de datos de la secuencia devueltos por `studentQuery3` es `IEnumerable(Of String)`, una secuencia de cadenas. Como en ejemplos anteriores, la asignación de datos de un tipo de `studentQuery3` queda por el compilador para determinar mediante la inferencia de tipo local.  
  
     [!code-vb[VbLINQWalkthrough&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  Sitúe el puntero del mouse sobre `studentQuery3` en el código para comprobar que el tipo asignado es `IEnumerable(Of String)`.  
  
3.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Para crear un tipo anónimo en la cláusula Select  
  
1.  Agregue el código de esta sección para ver cómo los tipos anónimos se utilizan en consultas. Utilizar en consultas cuando desea devolver varios campos del origen de datos en lugar de registros completos (`currentStudent` registros en ejemplos anteriores) o simples campos (`First` en la sección anterior). En lugar de definir un nuevo tipo con nombre que contiene los campos que desea incluir en el resultado, especifica los campos en el `Select` cláusula y el compilador crea un tipo anónimo con esos campos como propiedades. Para obtener más información, consulte [tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     En el ejemplo siguiente se crea una consulta que devuelve el nombre y la clasificación de ancianos cuyo grado académico esté entre 1 y 10, por orden de grado académico. En este ejemplo, el tipo de `studentQuery4` debe deducir, porque la `Select` cláusula devuelve una instancia de un tipo anónimo, y un tipo anónimo no tiene ningún nombre utilizable.  
  
     [!code-vb[VbLINQWalkthrough Nº&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  Compile y ejecute la aplicación presionando CTRL + F5. Tenga en cuenta los resultados en la ventana de consola.  
  
## <a name="additional-examples"></a>Ejemplos adicionales  
 Ahora que conoce los aspectos básicos, lo siguiente es una lista de ejemplos adicionales que ilustran la flexibilidad y eficacia de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consultas. Cada ejemplo va precedido de una breve descripción de lo que hace. Sitúe el puntero del mouse sobre la variable de resultado de consulta para cada consulta ver el tipo deducido. Use un `For Each` bucle para generar los resultados.  
  
 [!code-vb[VbLINQWalkthrough&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a>Información adicional  
 Cuando se haya familiarizado con los conceptos básicos del uso de consultas, está listo para leer la documentación y ejemplos para el tipo específico de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] proveedor que le interesen:  
  
 [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17)  
  
## <a name="see-also"></a>Vea también  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Inferencia de tipo local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)
