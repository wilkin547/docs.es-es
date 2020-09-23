---
title: Procedimiento para llamar a un procedimiento almacenado mediante LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: 7e5fecf0c4c0d3a561ec7d0c4ac03c9d9ce7f759
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075140"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Cómo: Llamar a un procedimiento almacenado usando LINQ (Visual Basic)

Language-Integrated Query (LINQ) facilita el acceso a la información de base de datos, incluidos los objetos de base de datos, como los procedimientos almacenados.  
  
 En el ejemplo siguiente se muestra cómo crear una aplicación que llama a un procedimiento almacenado en una base de datos de SQL Server. En el ejemplo se muestra cómo llamar a dos procedimientos almacenados diferentes en la base de datos. Cada procedimiento devuelve los resultados de una consulta. Un procedimiento toma parámetros de entrada y el otro procedimiento no toma parámetros.  
  
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
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Para agregar procedimientos almacenados a Object Relational Designer  
  
1. En **Explorador de servidores** / **Explorador de bases de datos**, expanda la conexión a la base de datos Northwind. Expanda la carpeta **Procedimientos almacenados** .  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo si hace doble clic en el archivo Northwind. dbml que agregó anteriormente.  
  
2. Haga clic en el procedimiento almacenado **sales by Year** y arrástrelo hasta el panel derecho del diseñador. Haga clic en el procedimiento almacenado de los **diez productos más caros** y arrástrelo al panel derecho del diseñador.  
  
3. Guarde los cambios y cierre el diseñador.  
  
4. Guarde el proyecto.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Para agregar código para mostrar los resultados de los procedimientos almacenados  
  
1. En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView> control al formulario de Windows Forms predeterminado para el proyecto, Form1.  
  
2. Haga doble clic en Form1 para agregar código a su `Load` evento.  
  
3. Cuando agregó procedimientos almacenados a Object Relational Designer, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto. Este objeto contiene el código que debe tener para obtener acceso a esos procedimientos. El <xref:System.Data.Linq.DataContext> nombre del objeto para el proyecto se basa en el nombre del archivo. dbml. Para este proyecto, el <xref:System.Data.Linq.DataContext> objeto se denomina `northwindDataContext` .  
  
     Puede crear una instancia de <xref:System.Data.Linq.DataContext> en el código y llamar a los métodos de procedimiento almacenado especificados por Object Relational Designer. Para enlazar con el <xref:System.Windows.Forms.DataGridView> objeto, puede que tenga que forzar la ejecución inmediata de la consulta llamando al <xref:System.Linq.Enumerable.ToList%2A> método en los resultados del procedimiento almacenado.  
  
     Agregue el código siguiente al `Load` evento para llamar a cualquiera de los procedimientos almacenados que se exponen como métodos para el contexto de datos.  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. Presione F5 para ejecutar el proyecto y ver los resultados.  
  
## <a name="see-also"></a>Vea también

- [LINQ](index.md)
- [Consultas](../../../language-reference/queries/index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [DataContext (Métodos) (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
