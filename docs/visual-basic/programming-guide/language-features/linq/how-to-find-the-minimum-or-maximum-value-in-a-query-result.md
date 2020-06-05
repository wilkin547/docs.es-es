---
title: Procedimiento para buscar los valores máximo y mínimo en el resultado de una consulta mediante LINQ
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
ms.openlocfilehash: a148d8b726da78261eda152fcaafdd64ea01bb24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404983"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta usando LINQ (Visual Basic)
Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server. En el ejemplo se determinan los valores mínimo y máximo de los resultados mediante el uso de las `Aggregate` `Group By` cláusulas y. Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md) y [cláusula Group by](../../../language-reference/queries/group-by-clause.md).  
  
 En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind. Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft. Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>Crear una conexión a una base de datos  
  
1. En Visual Studio, Abra **Explorador de servidores** / **Explorador de bases de datos** haciendo clic en **Explorador de servidores** / **Explorador de bases de datos** en el menú **Ver** .  
  
2. Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores** / **Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.  
  
3. Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Para agregar un proyecto que contiene un archivo LINQ to SQL  
  
1. En Visual Studio, en el menú **archivo** , seleccione **nuevo** y haga clic en **proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.  
  
2. En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione la plantilla de elementos **LINQ to SQL clases** .  
  
3. Ponga al archivo el nombre `northwind.dbml`. Haga clic en **Agregar**. El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>Agregar tablas para realizar consultas en Object Relational Designer  
  
1. En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind. Expanda la carpeta **Tablas** .  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.  
  
2. Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador. Haga clic en la tabla Orders y arrástrela hasta el panel izquierdo del diseñador.  
  
     El diseñador crea `Customer` objetos y nuevos `Order` para el proyecto. Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea las propiedades secundarias de los objetos relacionados. Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.  
  
3. Guarde los cambios y cierre el diseñador.  
  
4. Guarde el proyecto.  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>Agregar código para consultar la base de datos y mostrar los resultados  
  
1. En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.  
  
2. Haga doble clic en Form1 para agregar código al `Load` evento del formulario.  
  
3. Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto. Este objeto contiene el código que debe tener para obtener acceso a esas tablas, además de colecciones y objetos individuales para cada tabla. El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml. Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .  
  
     Puede crear una instancia de en el <xref:System.Data.Linq.DataContext> código y consultar las tablas especificadas por Object Relational Designer.  
  
     Agregue el código siguiente al `Load` evento. En este código se consultan las tablas que se exponen como propiedades del contexto de datos y se determinan los valores mínimo y máximo de los resultados. En el ejemplo se usa la `Aggregate` cláusula para consultar un solo resultado y la `Group By` cláusula para mostrar un promedio de los resultados agrupados.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. Presione **F5** para ejecutar el proyecto y ver los resultados.  
  
## <a name="see-also"></a>Consulte también

- [LINQ](index.md)
- [Consultas](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext (métodos) (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
