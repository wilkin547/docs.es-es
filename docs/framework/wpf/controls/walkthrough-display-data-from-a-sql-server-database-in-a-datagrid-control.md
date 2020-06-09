---
title: 'Tutorial: Mostrar los datos de una base de datos de SQL Server en un control DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 1398d8408a0b85d6603d638312e92ba35c5e77d3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591038"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Tutorial: Mostrar datos de una base de datos de SQL Server en un control DataGrid

En este tutorial, recuperará datos de una base de datos de SQL Server y mostrará los datos en un <xref:System.Windows.Controls.DataGrid> control. Use el Entity Framework ADO.NET para crear las clases de entidad que representan los datos y use LINQ para escribir una consulta que recupere los datos especificados de una clase de entidad.

## <a name="prerequisites"></a>Requisitos previos

Necesitará los componentes siguientes para completar este tutorial:

- Visual Studio.

- Acceso a una instancia en ejecución de SQL Server o SQL Server Express que tenga adjunta la base de datos de ejemplo AdventureWorks. Puede descargar la base de datos AdventureWorks desde [GitHub](https://github.com/Microsoft/sql-server-samples/releases).

## <a name="create-entity-classes"></a>Crear clases de entidad

1. Cree un nuevo proyecto de aplicación de WPF en Visual Basic o C# y asígnele el nombre `DataGridSQLExample` .

2. En Explorador de soluciones, haga clic con el botón secundario en el proyecto, seleccione **Agregar**y, a continuación, seleccione **nuevo elemento**.

     Aparece el cuadro de diálogo Agregar nuevo elemento.

3. En el panel Plantillas instaladas, seleccione **datos** y, en la lista de plantillas, seleccione **ADO.NET Entity Data Model**.

     ![ADO.NET plantilla de elementos de Entity Data Model](../../wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4. Asigne un nombre al archivo `AdventureWorksModel.edmx` y haga clic en **Agregar**.

     Aparecerá el Asistente para Entity Data Model.

5. En la pantalla elegir contenido del modelo, seleccione **EF Designer desde base de datos** y, a continuación, haga clic en **siguiente**.

6. En la pantalla elegir la conexión de datos, proporcione la conexión a la base de datos de AdventureWorksLT2008. Para obtener más información, vea [cuadro de diálogo elegir la conexión de datos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).

    Asegúrese de que el nombre es `AdventureWorksLT2008Entities` y de que la casilla **Guardar configuración de conexión de entidad en App. config como** está activada y, a continuación, haga clic en **siguiente**.

7. En la pantalla elegir los objetos de base de datos, expanda el nodo tablas y seleccione las tablas **Product** y **ProductCategory** .

     Puede generar clases de entidad para todas las tablas; sin embargo, en este ejemplo solo se recuperan datos de esas dos tablas.

     ![Seleccionar Product y ProductCategory de las tablas](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")

8. Haga clic en **Finalizar**

     Las entidades Product y ProductCategory se muestran en Entity Designer.

     ![Modelos de entidad de Product y ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")

## <a name="retrieve-and-present-the-data"></a>Recuperación y presentación de los datos

1. Abra el archivo MainWindow. Xaml.

2. Establezca la <xref:System.Windows.FrameworkElement.Width%2A> propiedad del en <xref:System.Windows.Window> 450.

3. En el editor XAML, agregue la siguiente <xref:System.Windows.Controls.DataGrid> etiqueta entre las `<Grid>` `</Grid>` etiquetas y para agregar un <xref:System.Windows.Controls.DataGrid> denominado `dataGrid1` .

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     ![Ventana con DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")

4. Seleccione <xref:System.Windows.Window>.

5. Con el editor de ventana Propiedades o XAML, cree un controlador de eventos para el <xref:System.Windows.Window> denominado `Window_Loaded` para el <xref:System.Windows.FrameworkElement.Loaded> evento. Para obtener más información, vea [Cómo: crear un controlador de eventos simple](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

     A continuación se muestra el código XAML de MainWindow. Xaml.

    > [!NOTE]
    > Si está utilizando Visual Basic, en la primera línea de MainWindow. XAML, reemplace `x:Class="DataGridSQLExample.MainWindow"` por `x:Class="MainWindow"` .

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. Abra el archivo de código subyacente (MainWindow. Xaml. vb o MainWindow.xaml.cs) para el <xref:System.Windows.Window> .

7. Agregue el código siguiente para recuperar solo los valores específicos de las tablas combinadas y establecer la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de <xref:System.Windows.Controls.DataGrid> en los resultados de la consulta.

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. Ejecute el ejemplo.

     Debería ver <xref:System.Windows.Controls.DataGrid> que muestra los datos.

     ![DataGrid con datos de base de datos SQL](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.DataGrid>
