---
title: Filtrar Buscar el valor mínimo o máximo en un resultado de consulta usando LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: 311ba2d9c4be75e77cf134bf44dc96eab957736d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838175"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Filtrar Buscar el valor mínimo o máximo en un resultado de consulta usando LINQ (Visual Basic)
Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y ejecutar consultas.  
  
 El ejemplo siguiente muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server. El ejemplo determina los valores mínimos y máximo para los resultados mediante el uso de la `Aggregate` y `Group By` cláusulas. Para obtener más información, consulte [cláusula Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) y [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
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
  
     Agregue el código siguiente a la `Load` eventos. Este código consulta las tablas que se exponen como propiedades de su contexto de datos y determina los valores mínimos y máximo para los resultados. El ejemplo se usa `Aggregate` cláusula para consultar un único resultado y el `Group By` cláusula para mostrar un promedio para agrupar los resultados.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4.  Presione F5 para ejecutar el proyecto y ver los resultados.  
  
## <a name="see-also"></a>Vea también

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Métodos DataContext (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
