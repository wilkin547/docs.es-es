---
title: Buscar los valores máximo y mínimo en el resultado de una consulta usando LINQ
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
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112367"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a>Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta usando LINQ (Visual Basic)
Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y la ejecución de consultas.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server. El ejemplo determina los valores mínimo y máximo `Aggregate` `Group By` para los resultados mediante las cláusulas y. Para obtener más información, consulte [Cláusula agregada](../../../../visual-basic/language-reference/queries/aggregate-clause.md) y Cláusula de [grupo](../../../../visual-basic/language-reference/queries/group-by-clause.md)por .  
  
 Los ejemplos de este tema usan la base de datos de ejemplo Northwind. Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del Centro de descarga de Microsoft. Para obtener instrucciones, consulte [Descarga de bases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)de datos de ejemplo .  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a>Crear una conexión a una base de datos  
  
1. En Visual Studio, abra el Explorador de**bases** de datos del **Explorador**/de servidores haciendo clic en Explorador de bases de datos del **Server Explorer**/**Explorador** de servidores en el menú **Ver.**  
  
2. Haga clic con el botón secundario en **Conexiones** de datos en el**Explorador** de bases de datos del **Explorador**/de servidores y, a continuación, haga clic en **Agregar conexión**.  
  
3. Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Para agregar un proyecto que contiene un archivo LINQ to SQLLINQ to SQL  
  
1. En Visual Studio, en **el** archivo menú, seleccione **nuevo** y, a continuación, haga clic en **proyecto**. Seleccione Aplicación de **formularios Windows Forms** de Visual Basic como tipo de proyecto.  
  
2. En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione la plantilla de elemento **LINQ to SQL Classes.**  
  
3. Asigne el nombre `northwind.dbml` al archivo. Haga clic en **Agregar**. Object Relational Designer (O/R Designer) se abre para el archivo northwind.dbml.  
  
## <a name="add-tables-to-query-to-the-or-designer"></a>Agregar tablas para consultar al Diseñador de O/R  
  
1. En el**Explorador**de bases de datos del **Explorador**/de servidores , expanda la conexión a la base de datos Northwind. Expanda la carpeta **Tablas** .  
  
     Si ha cerrado el Diseñador de O/R, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.  
  
2. Haga clic en la tabla Customers y arrástrela al panel izquierdo del diseñador. Haga clic en la tabla Orders y arrástrela al panel izquierdo del diseñador.  
  
     El diseñador `Customer` crea `Order` nuevos y objetos para el proyecto. Observe que el diseñador detecta automáticamente las relaciones entre las tablas y crea propiedades secundarias para los objetos relacionados. Por ejemplo, IntelliSense mostrará `Customer` que `Orders` el objeto tiene una propiedad para todos los pedidos relacionados con ese cliente.  
  
3. Guarde los cambios y cierre el diseñador.  
  
4. Guarde el proyecto.  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a>Agregue código para consultar la base de datos y mostrar los resultados  
  
1. En el **cuadro** <xref:System.Windows.Forms.DataGridView> de herramientas , arrastre un control al formulario Windows Forms predeterminado para el proyecto, Form1.  
  
2. Haga doble clic en Form1 `Load` para agregar código al evento del formulario.  
  
3. Al agregar tablas al Diseñador de O/R, el diseñador agregó un <xref:System.Data.Linq.DataContext> objeto para el proyecto. Este objeto contiene el código que debe tener para tener acceso a esas tablas, además de objetos individuales y colecciones para cada tabla. El <xref:System.Data.Linq.DataContext> objeto del proyecto se denomina en función del nombre del archivo .dbml. Para este proyecto, <xref:System.Data.Linq.DataContext> el `northwindDataContext`objeto se denomina .  
  
     Puede crear una instancia <xref:System.Data.Linq.DataContext> del código y consultar las tablas especificadas por el Diseñador de O/R.  
  
     Agregue el código `Load` siguiente al evento. Este código consulta las tablas que se exponen como propiedades del contexto de datos y determina los valores mínimo y máximo de los resultados. El ejemplo `Aggregate` usa la cláusula para consultar `Group By` un único resultado y la cláusula para mostrar un promedio para los resultados agrupados.  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. Presione **F5** para ejecutar el proyecto y ver los resultados.  
  
## <a name="see-also"></a>Consulte también

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [LINQ a SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Métodos DataContext (Diseñador de O/R)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
