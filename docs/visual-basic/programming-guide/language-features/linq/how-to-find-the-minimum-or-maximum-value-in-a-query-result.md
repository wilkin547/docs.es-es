---
title: 'Cómo: buscar el valor mínimo o máximo en el resultado de una consulta mediante LINQ'
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
ms.openlocfilehash: bddb90baa0b01fd9d724583b472af9f9fa7569e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344980"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta usando LINQ (Visual Basic)
Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos y la ejecución de consultas.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server. En el ejemplo se determinan los valores mínimo y máximo de los resultados mediante el uso de las cláusulas `Aggregate` y `Group By`. Para obtener más información, vea [cláusula Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) y [cláusula Group by](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 En los ejemplos de este tema se utiliza la base de datos de ejemplo Northwind. Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft. Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Para crear una conexión a una base de datos  
  
1. En Visual Studio, Abra **Explorador de servidores**/**Explorador de bases de datos** haciendo clic en **Explorador de servidores**/**Explorador de bases de datos** en el menú **Ver** .  
  
2. Haga clic con el botón secundario en **conexiones de datos** en **Explorador de servidores**/**Explorador de bases de datos** y, a continuación, haga clic en **Agregar conexión**.  
  
3. Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Para agregar un proyecto que contiene un archivo LINQ to SQL  
  
1. En el menú **Archivo** de Visual Studio, apunte a **Nuevo** y haga clic en **Proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.  
  
2. En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione la plantilla de elementos **LINQ to SQL clases** .  
  
3. Asigne al archivo el nombre `northwind.dbml`. Haga clic en **Agregar**. El Object Relational Designer (Object Relational Designer) se abre para el archivo Northwind. dbml.  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a>Para agregar tablas que se van a consultar en Object Relational Designer  
  
1. En **Explorador de servidores**/**Explorador de bases de datos**, expanda la conexión a la base de datos Northwind. Expanda la carpeta **tablas** .  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.  
  
2. Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador. Haga clic en la tabla Orders y arrástrela hasta el panel izquierdo del diseñador.  
  
     El diseñador crea nuevos objetos `Customer` y `Order` para el proyecto. Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea las propiedades secundarias de los objetos relacionados. Por ejemplo, IntelliSense mostrará que el objeto `Customer` tiene una propiedad `Orders` para todos los pedidos relacionados con ese cliente.  
  
3. Guarde los cambios y cierre el diseñador.  
  
4. Guarde el proyecto.  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Para agregar código para consultar la base de datos y mostrar los resultados  
  
1. En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.DataGridView> al formulario predeterminado de Windows para el proyecto, Form1.  
  
2. Haga doble clic en Form1 para agregar código al evento `Load` del formulario.  
  
3. Al agregar tablas a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto. Este objeto contiene el código que debe tener para obtener acceso a esas tablas, además de colecciones y objetos individuales para cada tabla. El nombre del objeto <xref:System.Data.Linq.DataContext> del proyecto se basa en el nombre del archivo. dbml. Para este proyecto, el objeto de <xref:System.Data.Linq.DataContext> se denomina `northwindDataContext`.  
  
     Puede crear una instancia de la <xref:System.Data.Linq.DataContext> en el código y consultar las tablas especificadas por Object Relational Designer.  
  
     Agregue el código siguiente al evento `Load`. En este código se consultan las tablas que se exponen como propiedades del contexto de datos y se determinan los valores mínimo y máximo de los resultados. En el ejemplo se usa la cláusula `Aggregate` para consultar un solo resultado y la cláusula `Group By` para mostrar un promedio de los resultados agrupados.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. Presione F5 para ejecutar el proyecto y ver los resultados.  
  
## <a name="see-also"></a>Vea también

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Métodos DataContext (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
