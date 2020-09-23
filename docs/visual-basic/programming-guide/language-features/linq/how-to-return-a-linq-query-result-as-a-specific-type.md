---
title: Procedimiento para devolver el resultado de una consulta con LINQ como tipo específico
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 249c3eebaeec3d09a297fead07ab056caff1b618
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071812"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a>Cómo: Devolver el resultado de una consulta con LINQ como tipo específico (Visual Basic)

Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas. De forma predeterminada, las consultas LINQ devuelven una lista de objetos como un tipo anónimo. También puede especificar que una consulta devuelva una lista de un tipo específico mediante la `Select` cláusula.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y proyecta los resultados como un tipo con nombre específico. Para obtener más información, vea [tipos anónimos](../objects-and-classes/anonymous-types.md) y [cláusula SELECT](../../../language-reference/queries/select-clause.md).  
  
 En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind. Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft. Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Para crear una conexión a una base de datos  
  
1. En Visual Studio, Abra **Explorador de servidores** / **Explorador de bases de datos** haciendo clic en **Explorador de servidores** / **Explorador de bases de datos** en el menú **Ver** .  
  
2. Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.  
  
3. Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Para agregar un proyecto que contiene un archivo LINQ to SQL  
  
1. En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.  
  
2. En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione la plantilla de elementos **LINQ to SQL clases** .  
  
3. Ponga al archivo el nombre `northwind.dbml`. Haga clic en **Agregar**. El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Para agregar tablas que se van a consultar en Object Relational Designer  
  
1. En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind. Expanda la carpeta **Tablas** .  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.  
  
2. Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador.  
  
     El diseñador crea un nuevo `Customer` objeto para el proyecto. Puede proyectar el resultado de una consulta como el `Customer` tipo o como un tipo que cree. En este ejemplo se creará un nuevo tipo en un procedimiento posterior y se proyectará un resultado de consulta como ese tipo.  
  
3. Guarde los cambios y cierre el diseñador.  
  
4. Guarde el proyecto.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Para agregar código para consultar la base de datos y mostrar los resultados  
  
1. En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.  
  
2. Haga doble clic en Form1 para modificar la clase Form1.  
  
3. Después de la `End Class` instrucción de la clase Form1, agregue el código siguiente para crear un `CustomerInfo` tipo que contenga los resultados de la consulta para este ejemplo.  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto al proyecto. Este objeto contiene el código que debe tener para obtener acceso a esas tablas y para obtener acceso a objetos y colecciones individuales para cada tabla. El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml. Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .  
  
     Puede crear una instancia de en el <xref:System.Data.Linq.DataContext> código y consultar las tablas especificadas por Object Relational Designer.  
  
     En el `Load` caso de la clase Form1, agregue el siguiente código para consultar las tablas que se exponen como propiedades de su contexto de datos. La `Select` cláusula de la consulta creará un nuevo `CustomerInfo` tipo en lugar de un tipo anónimo para cada elemento del resultado de la consulta.  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. Presione F5 para ejecutar el proyecto y ver los resultados.  
  
## <a name="see-also"></a>Vea también

- [LINQ](index.md)
- [Consultas](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext (Métodos) (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
