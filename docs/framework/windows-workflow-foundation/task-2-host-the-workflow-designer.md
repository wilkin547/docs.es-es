---
title: 'Tarea 2: Hospedar el diseñador de flujo de trabajo'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 92c5fa347cc7a2c0088ab8f4fbdfddf25ffb83c1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037870"
---
# <a name="task-2-host-the-workflow-designer"></a>Tarea 2: Hospedar el diseñador de flujo de trabajo

[!INCLUDE[wfd1](../../../includes/wfd1-md.md)] En este tema se describe el procedimiento para hospedar una instancia de en una aplicación Windows Presentation Foundation (WPF).

El procedimiento configura el control de **cuadrícula** que contiene el diseñador, crea mediante programación una instancia de <xref:System.Activities.Presentation.WorkflowDesigner> que contiene una actividad predeterminada <xref:System.Activities.Statements.Sequence> , registra los metadatos del diseñador para proporcionar compatibilidad con el diseñador para todos las actividades integradas y hospedan [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] en la aplicación WPF.

### <a name="to-host-the-workflow-designer"></a>Para hospedar el diseñador de flujo de trabajo

1. Abra el proyecto HostingApplication que creó en [la tarea 1: Cree una nueva aplicación](task-1-create-a-new-wpf-app.md)Windows Presentation Foundation.

2. Ajuste el tamaño de la ventana para facilitar el uso de [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. Para ello, seleccione **MainWindow** en el diseñador, presione F4 para mostrar la ventana **propiedades** y, en la sección de **diseño** , establezca el **ancho** en un valor de 600 y el **alto** en un valor de 350.

3. Para establecer el nombre de la cuadrícula, seleccione el panel de **cuadrícula** en el diseñador (haga clic en el cuadro dentro de **MainWindow**) y establezca la propiedad **nombre** en la parte superior de la ventana **propiedades** en "Grid1".

4. En la ventana **propiedades** , haga clic en los puntos suspensivos ( **...** ) `ColumnDefinitions` junto a la propiedad para abrir el cuadro de diálogo Editor de la **colección** .

5. En el cuadro de diálogo **Editor de colecciones** , haga clic en el botón **Agregar** tres veces para insertar tres columnas en el diseño. La primera columna contendrá el **cuadro de herramientas**, la segunda columna hospedará [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]y la tercera columna se utilizará para el inspector de propiedad.

6. Establezca la `Width` propiedad de la columna central en el valor "4 *".

7. Haga clic en **Aceptar** para guardar los cambios. El siguiente XAML se agrega a su archivo MainWindow.xaml:

    ```xml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. En **Explorador de soluciones**, haga clic con el botón secundario en MainWindow. XAML y seleccione **Ver código**. Modifique el código siguiendo estos pasos:

    1. Agregue los siguientes espacios de nombres:

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. Para declarar un campo de miembro privado que hospede una instancia de <xref:System.Activities.Presentation.WorkflowDesigner>, agregue el siguiente código a la clase `MainWindow`.

        ```csharp
        public partial class MainWindow : Window
        {
            private WorkflowDesigner wd;

            public MainWindow()
            {
                InitializeComponent();
            }
        }
        ```

    3. Agregue el método `AddDesigner` siguiente a la clase `MainWindow`. La implementación crea una instancia de <xref:System.Activities.Presentation.WorkflowDesigner>, le agrega una <xref:System.Activities.Statements.Sequence> actividad y la coloca en la columna central de la **cuadrícula**de Grid1.

        ```csharp
        private void AddDesigner()
        {
            //Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            //Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            //Load a new Sequence as default.
            this.wd.Load(new Sequence());

            //Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }
        ```

    4. Registre los metadatos del diseñador para agregar la compatibilidad con el diseñador para todas las actividades integradas. Esto le permite colocar las actividades del cuadro de herramientas en la actividad <xref:System.Activities.Statements.Sequence> original en [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. Para ello, agregue el método `RegisterMetadata` a la clase `MainWindow`.

        ```csharp
        private void RegisterMetadata()
        {
            DesignerMetadata dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        Para obtener más información acerca del registro de diseñadores de [actividad, consulte How to: Cree un diseñador](how-to-create-a-custom-activity-designer.md)de actividad personalizado.

    5. En el constructor de clases `MainWindow`, agregue llamadas a los métodos declarados previamente para registrar los metadatos a fin de ser compatibles con el diseñador y crear <xref:System.Activities.Presentation.WorkflowDesigner>.

        ```csharp
        public MainWindow()
        {
            InitializeComponent();

            // Register the metadata
            RegisterMetadata();

            // Add the WFF Designer
            AddDesigner();
        }
        ```

        > [!NOTE]
        > El método `RegisterMetadata` registra los metadatos del diseñador de actividades integradas incluida la actividad <xref:System.Activities.Statements.Sequence>. Puesto que el método `AddDesigner` usa la actividad <xref:System.Activities.Statements.Sequence>, es necesario llamar primero al método `RegisterMetadata`.

9. Presione F5 para compilar y ejecutar la solución.

10. Consulte [tarea 3: Cree los paneles](task-3-create-the-toolbox-and-propertygrid-panes.md) Toolbox y PropertyGrid para obtener información sobre cómo agregar compatibilidad con el **cuadro de herramientas** y **PropertyGrid** al diseñador de flujo de trabajo hospedado en otro host.

## <a name="see-also"></a>Vea también

- [Rehospedaje del Diseñador de flujo de trabajo](rehosting-the-workflow-designer.md)
- [Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Tarea 3: Crear los paneles cuadro de herramientas y PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md)
