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
ms.openlocfilehash: 274ec2e8ef16190da53061bb197bc3b1a1fadcf8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024109"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Tutorial: Mostrar los datos de una base de datos de SQL Server en un control DataGrid

En este tutorial, recuperar datos de una base de datos de SQL Server y mostrar dichos datos en un <xref:System.Windows.Controls.DataGrid> control. Usar ADO.NET Entity Framework para crear las clases de entidad que representan los datos y usar LINQ para escribir una consulta que recupera los datos especificados de una clase de entidad.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio.

- Acceso a una instancia en ejecución de SQL Server o SQL Server Express que tiene la base de datos de ejemplo AdventureWorks conectada a ella. Puede descargar la base de datos de AdventureWorks desde el [GitHub](https://github.com/Microsoft/sql-server-samples/releases).

## <a name="create-entity-classes"></a>Crear clases de entidad

1. Cree un nuevo proyecto de aplicación de WPF en Visual Basic o C# y asígnele el nombre `DataGridSQLExample`.

2. En el Explorador de soluciones, haga clic en el proyecto, seleccione **agregar**y, a continuación, seleccione **nuevo elemento**.

     Aparece el cuadro de diálogo Agregar nuevo elemento.

3. En el panel Plantillas instaladas, seleccione **datos** y en la lista de plantillas, seleccione **ADO.NET Entity Data Model**.

     ![Plantilla de elemento de Entity Data Model ADO.NET](../../wcf/feature-details/./media/ado-net-entity-data-model-item-template.png)

4. Nombre del archivo `AdventureWorksModel.edmx` y, a continuación, haga clic en **agregar**.

     Aparecerá el Asistente para Entity Data Model.

5. En la pantalla Elegir contenido del modelo, seleccione **EF Designer de base de datos** y, a continuación, haga clic en **siguiente**.

6. En la pantalla Elegir la conexión de datos, proporcione la conexión a la base de datos AdventureWorksLT2008. Para obtener más información, consulte [elija el cuadro de diálogo de conexión de datos](https://go.microsoft.com/fwlink/?LinkId=160190).

    Asegúrese de que el nombre es `AdventureWorksLT2008Entities` y que la **Guardar configuración de conexión de entidad en App.Config como** casilla de verificación está seleccionada y, a continuación, haga clic en **siguiente**.

7. En la pantalla Elegir los objetos de base de datos, expanda el nodo tablas y seleccione el **producto** y **ProductCategory** tablas.

     Puede generar clases de entidad para todas las tablas; Sin embargo, en este ejemplo solo recuperar datos de esas dos tablas.

     ![Seleccionar Product y ProductCategory de las tablas](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")

8. Haga clic en **Finalizar**.

     Las entidades Product y ProductCategory se muestran en el Diseñador de entidades.

     ![Modelos de entidad de Product y ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")

## <a name="retrieve-and-present-the-data"></a>Recuperar y presentar los datos

1. Abra el archivo MainWindow.xaml.

2. Establecer el <xref:System.Windows.FrameworkElement.Width%2A> propiedad en el <xref:System.Windows.Window> a 450.

3. En el editor XAML, agregue el siguiente <xref:System.Windows.Controls.DataGrid> etiqueta entre el `<Grid>` y `</Grid>` etiquetas para agregar un <xref:System.Windows.Controls.DataGrid> denominado `dataGrid1`.

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     ![Ventana con DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")

4. Seleccione el control <xref:System.Windows.Window>.

5. Con la ventana Propiedades o el editor XAML, cree un controlador de eventos para el <xref:System.Windows.Window> denominado `Window_Loaded` para el <xref:System.Windows.FrameworkElement.Loaded> eventos. Para obtener más información, vea [Cómo: Crear un controlador de eventos Simple](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

     A continuación muestra el XAML de MainWindow.xaml.

    > [!NOTE]
    > Si utiliza Visual Basic, en la primera línea de MainWindow.xaml, reemplace `x:Class="DataGridSQLExample.MainWindow"` con `x:Class="MainWindow"`.

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. Abra el archivo de código subyacente (MainWindow.xaml.vb o MainWindow.xaml.cs) para el <xref:System.Windows.Window>.

7. Agregue el código siguiente para recuperar solo los valores específicos de las tablas combinadas y establecer el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.DataGrid> a los resultados de la consulta.

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. Ejecute el ejemplo.

     Debería ver un <xref:System.Windows.Controls.DataGrid> que muestra los datos.

     ![DataGrid con datos de la base de datos SQL](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.DataGrid>
- [¿Cómo lo hago?: ¿Introducción a Entity Framework en aplicaciones WPF?](https://go.microsoft.com/fwlink/?LinkId=159868)