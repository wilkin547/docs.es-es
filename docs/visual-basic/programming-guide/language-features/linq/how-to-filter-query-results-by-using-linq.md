---
title: Procedimiento Filtrar los resultados de consulta usando LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: 9aa3219cb613082545c0a417ed6972bb51c8815f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975412"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a>Procedimiento Filtrar los resultados de consulta usando LINQ (Visual Basic)
Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y ejecutar consultas.  
  
 El ejemplo siguiente muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server y filtra los resultados por un valor concreto mediante la `Where` cláusula. Para obtener más información, consulte [cláusula Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
 Los ejemplos de este tema usan la base de datos de ejemplo Northwind. Si no tiene esta base de datos en el equipo de desarrollo, puede descargarlo desde Microsoft Download Center. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Para crear una conexión a una base de datos  
  
1.  En Visual Studio, abra **Explorador de servidores**/**Database Explorer** haciendo **Explorador de servidores**/**base de datos Explorador** en el **vista** menú.  
  
2.  Haga clic en **conexiones de datos** en **Explorador de servidores**/**Database Explorer** y, a continuación, haga clic en **Agregar conexión**.  
  
3.  Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Para agregar un proyecto que contiene un archivo LINQ to SQL  
  
1.  En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.  
  
2.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione el **clases LINQ to SQL** plantilla de elemento.  
  
3.  Asigne al archivo el nombre `northwind.dbml`. Haga clic en **Agregar**. Se abre el Object Relational Designer (Object Relational Designer) para el archivo northwind.dbml.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Para agregar tablas a la consulta en el Object Relational Designer  
  
1.  En **Explorador de servidores**/**Database Explorer**, expanda la conexión a la base de datos Northwind. Expanda el **tablas** carpeta.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.  
  
2.  Haga clic en la tabla Customers y arrástrelo hasta el panel izquierdo del diseñador. Haga clic en la tabla Orders y arrástrelo hasta el panel izquierdo del diseñador.  
  
     El diseñador crea nuevos `Customer` y `Order` objetos para el proyecto. Tenga en cuenta que el diseñador automáticamente detecta las relaciones entre las tablas y crea las propiedades de los objetos relacionados de secundarios. Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` relacionados con la propiedad de todos los pedidos para ese cliente.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Para agregar código para consultar la base de datos y mostrar los resultados  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control en el formulario de Windows predeterminada para el proyecto, Form1.  
  
2.  Haga doble clic en Form1 para agregar código a la `Load` evento del formulario.  
  
3.  Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext> objeto para el proyecto. Este objeto contiene el código que debe tener para tener acceso a esas tablas, además de los objetos individuales y colecciones para cada tabla. La <xref:System.Data.Linq.DataContext> objeto para el proyecto se denomina según el nombre del archivo dbml. Para este proyecto, el <xref:System.Data.Linq.DataContext> se denomina objeto `northwindDataContext`.  
  
     Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especifican por el Object Relational Designer.  
  
     Agregue el código siguiente a la `Load` que consultar las tablas que se exponen como propiedades del contexto de datos de evento. La consulta filtra los resultados y devuelve solo los clientes que se encuentran en `London`.  
  
     [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]  
  
4.  Presione F5 para ejecutar el proyecto y ver los resultados.  
  
5.  Estos son algunos otros filtros que puede probar.  
  
     [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]  
  
## <a name="see-also"></a>Vea también
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Métodos DataContext (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
