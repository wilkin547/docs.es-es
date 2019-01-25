---
title: 'Tarea 2: Hospedar el Diseñador de flujo de trabajo'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: e8895e4b2c90f189c88ec3a803615e736dada455
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572778"
---
# <a name="task-2-host-the-workflow-designer"></a>Tarea 2: Hospedar el Diseñador de flujo de trabajo
Este tema describe el procedimiento para hospedar una instancia de la [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] en una aplicación de Windows Presentation Foundation (WPF).  
  
 El procedimiento se configura el **cuadrícula** control que contiene el diseñador, se crea mediante programación una instancia de la <xref:System.Activities.Presentation.WorkflowDesigner> que contiene el valor predeterminado es <xref:System.Activities.Statements.Sequence> actividad, registra los metadatos del diseñador para proporcionar compatibilidad con el diseñador para las actividades integradas en todos los hosts y el [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] en el [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] aplicación.  
  
### <a name="to-host-the-workflow-designer"></a>Para hospedar el diseñador de flujo de trabajo  
  
1.  Abra el proyecto HostingApplication que creó en [tarea 1: Crear una nueva aplicación de Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md).  
  
2.  Ajuste el tamaño de la ventana para facilitar el uso de [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. Para ello, seleccione **MainWindow** en el diseñador, presione F4 para mostrar la **propiedades** ventana y, en el **diseño** sección no existe, establezca el **deancho** en un valor de 600 y **alto** en un valor de 350.  
  
3.  Establezca el nombre de la cuadrícula seleccionando el **cuadrícula** panel en el diseñador (haga clic en el cuadro de la **MainWindow**) y configuración de la **nombre** propiedad en la parte superior de la  **Propiedades** ventana en "grid1".  
  
4.  En el **propiedades** ventana, haga clic en el botón de puntos suspensivos (**...** ) junto a la `ColumnDefinitions` propiedad para abrir el **Editor de la colección** cuadro de diálogo.  
  
5.  En el **Editor de la colección** cuadro de diálogo, haga clic en el **agregar** tres veces para insertar tres columnas en el diseño de botón. La primera columna contendrá el **cuadro de herramientas**, la segunda columna va a hospedar el [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], y la tercera columna se utilizará para el inspector de propiedad.  
  
6.  Establecer el `Width` propiedad de la columna central en el valor "4 *".  
  
7.  Haga clic en **Aceptar** para guardar los cambios. El siguiente XAML se agrega a su archivo MainWindow.xaml:  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8.  En **el Explorador de soluciones**, haga clic en MainWindow.xaml y seleccione **ver código**. Modifique el código siguiendo estos pasos:  
  
    1.  Agregue los siguientes espacios de nombres:  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  Para declarar un campo de miembro privado que hospede una instancia de <xref:System.Activities.Presentation.WorkflowDesigner>, agregue el siguiente código a la clase `MainWindow`.  
  
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
  
    3.  Agregue el método `AddDesigner` siguiente a la clase `MainWindow`. La implementación crea una instancia de la <xref:System.Activities.Presentation.WorkflowDesigner>, agrega un <xref:System.Activities.Statements.Sequence> actividad y lo coloca en la columna central de la grid1 **cuadrícula**.  
  
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
  
    4.  Registre los metadatos del diseñador para agregar la compatibilidad con el diseñador para todas las actividades integradas. Esto le permite colocar las actividades del cuadro de herramientas en la actividad <xref:System.Activities.Statements.Sequence> original en [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. Para ello, agregue el método `RegisterMetadata` a la clase `MainWindow`.  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         Para obtener más información sobre el registro de los diseñadores de actividad, vea [Cómo: Crear un diseñador de actividad personalizado](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md).  
  
    5.  En el constructor de clases `MainWindow`, agregue llamadas a los métodos declarados previamente para registrar los metadatos a fin de ser compatibles con el diseñador y crear <xref:System.Activities.Presentation.WorkflowDesigner>.  
  
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
        >  El método `RegisterMetadata` registra los metadatos del diseñador de actividades integradas incluida la actividad <xref:System.Activities.Statements.Sequence>. Puesto que el método `AddDesigner` usa la actividad <xref:System.Activities.Statements.Sequence>, es necesario llamar primero al método `RegisterMetadata`.  
  
9. Presione F5 para compilar y ejecutar la solución.  
  
10. Consulte [tarea 3: Crear el cuadro de herramientas y PropertyGrid paneles](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md) para obtener información sobre cómo agregar **cuadro de herramientas** y **PropertyGrid** soporte técnico para el Diseñador de flujo de trabajo rehospedado.  
  
## <a name="see-also"></a>Vea también
- [Rehospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)
- [Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)
- [Tarea 3: Crear el cuadro de herramientas y PropertyGrid paneles](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)
