---
title: "Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid
En esta tarea, creará los paneles **Cuadro de herramientas** y **PropertyGrid**, y los agregará al [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] rehospedado.  
  
 A modo de referencia, el código que debe incluir el archivo MainWindow.xaml.cs después de completar las tres tareas de la serie de temas [Rehospedar el Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md) se proporciona al final de este tema.  
  
### Para crear el Cuadro de herramientas y agregarlo a la cuadrícula  
  
1.  Abra el proyecto HostingApplication que obtuvo siguiendo el procedimiento descrito en [Tarea 2: Hospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md).  
  
2.  Haga clic con el botón secundario en el archivo MainWindow.xaml en el panel **Explorador de soluciones** y seleccione **Ver código**.  
  
3.  Agregue un método `GetToolboxControl` a la clase `MainWindow` que cree una clase <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, agregue una nueva categoría de **cuadro de herramientas** al **Cuadro de herramientas** y asigne los tipos de actividad <xref:System.Activities.Statements.Assign> y <xref:System.Activities.Statements.Sequence> a dicha categoría.  
  
    ```csharp  
  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
  
    ```  
  
4.  Agregue un método privado `AddToolbox` a la clase `MainWindow` para colocar el **Cuadro de herramientas** en la columna izquierda en la cuadrícula.  
  
    ```csharp  
  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
  
    ```  
  
5.  Agregue una llamada al método `AddToolBox` en el constructor de clase `MainWindow()` tal y como se muestra en el siguiente código.  
  
    ```csharp  
  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
  
    ```  
  
6.  Presione F5 para compilar y ejecutar la solución.Se debería mostrar el **cuadro de herramientas** que contiene las actividades <xref:System.Activities.Statements.Assign> y <xref:System.Activities.Statements.Sequence>.  
  
### Para crear PropertyGrid  
  
1.  Haga clic con el botón secundario en el archivo MainWindow.xaml en el panel **Explorador de soluciones** y seleccione **Ver código**.  
  
2.  Agregue el método `AddPropertyInspector` a la clase `MainWindow` para colocar el panel **PropertyGrid** en la columna situada más a la derecha en la cuadrícula.  
  
    ```csharp  
  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
  
    ```  
  
3.  Agregue una llamada al método `AddPropertyInspector` en el constructor de clase `MainWindow()` tal y como se muestra en el siguiente código.  
  
    ```csharp  
  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
        this.AddToolBox();  
  
        this.AddPropertyInspector();   
    }  
  
    ```  
  
4.  Presione F5 para compilar y ejecutar la solución.Se deberían mostrar todos los paneles \(el **Cuadro de herramientas**, el lienzo de diseño de flujo de trabajo y **PropertyGrid**\) y cuando arrastre una actividad <xref:System.Activities.Statements.Assign> o una actividad <xref:System.Activities.Statements.Sequence> al lienzo del diseño, la cuadrícula de propiedad debe actualizarse dependiendo de la actividad resaltada.  
  
## Ejemplo  
 El archivo MainWindow.xaml.cs debe contener ahora el siguiente código.  
  
```  
  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
//dlls added  
using System.Activities;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation;  
using System.Activities.Presentation.Metadata;  
using System.Activities.Presentation.Toolbox;  
using System.Activities.Statements;  
using System.ComponentModel;  
  
namespace HostingApplication  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
        private WorkflowDesigner wd;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
            RegisterMetadata();  
            AddDesigner();  
            this.AddToolBox();  
            this.AddPropertyInspector();  
        }  
  
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
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
                typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
            // Add the Toolbox items to the category.  
            category.Add(tool1);  
            category.Add(tool2);  
  
            // Add the category to the ToolBox control.  
            ctrl.Categories.Add(category);  
            return ctrl;  
        }  
  
        private void AddToolBox()  
        {  
            ToolboxControl tc = GetToolboxControl();  
            Grid.SetColumn(tc, 0);  
            grid1.Children.Add(tc);  
        }  
  
        private void AddPropertyInspector()  
        {  
            Grid.SetColumn(wd.PropertyInspectorView, 2);  
            grid1.Children.Add(wd.PropertyInspectorView);  
        }  
  
    }  
}  
  
```  
  
## Vea también  
 [Rehospedar el Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)   
 [Tarea 2: Hospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)