---
title: "Tarea 2: Hospedaje del Dise&#241;ador de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Tarea 2: Hospedaje del Dise&#241;ador de flujo de trabajo
En este tema se describe el procedimiento para hospedar una instancia de [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] en una aplicación [!INCLUDE[avalon1](../../../includes/avalon1-md.md)].  
  
 El procedimiento configura el control de **cuadrícula** que contiene el diseñador, crea mediante programación una instancia de la clase <xref:System.Activities.Presentation.WorkflowDesigner> que contiene una actividad <xref:System.Activities.Statements.Sequence> predeterminada, registra los metadatos del diseñador para proporcionar compatibilidad con el diseñador en todas las actividades integradas y hospeda el [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] en la aplicación [!INCLUDE[avalon2](../../../includes/avalon2-md.md)].  
  
### Para hospedar el diseñador de flujo de trabajo  
  
1.  Abra el proyecto HostingApplication que haya creado en [Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md).  
  
2.  Ajuste el tamaño de la ventana para facilitar el uso de [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].Para ello, seleccione **MainWindow** en el diseñador, presione F4 para mostrar la ventana **Propiedades** y, en la sección **Diseño**, defina **Ancho** en 600 y **Alto** en 350.  
  
3.  Establezca el nombre de la cuadrícula seleccionando el panel **Cuadrícula** en el diseñador \(haga clic en el cuadro dentro de **MainWindow**\) y estableciendo la propiedad **Nombre** en la parte superior de la ventana **Propiedades** en "grid1".  
  
4.  En la ventana **Propiedades**, haga clic en los puntos suspensivos \(**…**\) junto a la propiedad `ColumnDefinitions` para abrir el cuadro de diálogo **Editor de la colección**.  
  
5.  En el cuadro de diálogo **Editor de la colección**, haga clic en el botón **Agregar** tres veces para insertar tres columnas en el diseño.La primera columna contendrá el **cuadro de herramientas**, la segunda hospedará [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]y la tercera se usará para el inspector de propiedad.  
  
6.  Establezca la propiedad `Width` de la columna central en el valor "4\*".  
  
7.  Haga clic en **Aceptar** para guardar los cambios.El siguiente XAML se agrega a su archivo MainWindow.xaml:  
  
    ```  
  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
  
    ```  
  
8.  En el **Explorador de soluciones**, haga clic con el botón secundario en MainWindow.xaml y seleccione **Ver código**.Modifique el código siguiendo estos pasos:  
  
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
  
    3.  Agregue el método `AddDesigner` siguiente a la clase `MainWindow`.La implementación crea una instancia de <xref:System.Activities.Presentation.WorkflowDesigner>, le agrega una actividad <xref:System.Activities.Statements.Sequence> y la coloca en la columna central de la **cuadrícula** grid1.  
  
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
  
    4.  Registre los metadatos del diseñador para agregar la compatibilidad con el diseñador para todas las actividades integradas.Esto le permite colocar las actividades del cuadro de herramientas en la actividad <xref:System.Activities.Statements.Sequence> original en [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].Para ello, agregue el método `RegisterMetadata` a la clase `MainWindow`.  
  
        ```csharp  
  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        ```  
  
         [!INCLUDE[crabout](../../../includes/crabout-md.md)] el registro de diseñadores de actividad, vea [Cómo: Crear un diseñador de actividad personalizado](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-activity-designer.md).  
  
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
        >  El método `RegisterMetadata` registra los metadatos del diseñador de actividades integradas incluida la actividad <xref:System.Activities.Statements.Sequence>.Puesto que el método `AddDesigner` usa la actividad <xref:System.Activities.Statements.Sequence>, es necesario llamar primero al método `RegisterMetadata`.  
  
9. Presione F5 para compilar y ejecutar la solución.  
  
10. Vea [Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid](../../../docs/framework/windows-workflow-foundation//task-3-create-the-toolbox-and-propertygrid-panes.md) para obtener información sobre cómo agregar la compatibilidad para el **cuadro de herramientas** y **PropertyGrid** a su diseñador de flujo de trabajo rehospedado.  
  
## Vea también  
 [Rehospedar el Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)   
 [Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid](../../../docs/framework/windows-workflow-foundation//task-3-create-the-toolbox-and-propertygrid-panes.md)