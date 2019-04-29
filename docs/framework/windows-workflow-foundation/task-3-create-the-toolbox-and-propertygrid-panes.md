---
title: 'Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 15e5b4ea08b6bc243484b6963c1c06f448bb985b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641545"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid
En esta tarea, creará el **cuadro de herramientas** y **PropertyGrid** paneles y agregarlos a rehospedado [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].  
  
 Como referencia, el código que debe estar en el archivo MainWindow.xaml.cs después de completar las tres tareas en el [Rehospedar el Diseñador de flujo de trabajo](rehosting-the-workflow-designer.md) serie de temas se proporciona al final de este tema.  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>Para crear el Cuadro de herramientas y agregarlo a la cuadrícula  
  
1. Abra el proyecto HostingApplication que obtuvo siguiendo el procedimiento descrito en [tarea 2: Hospedar el Diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md).  
  
2. En el **el Explorador de soluciones** panel, haga clic en el archivo MainWindow.xaml y seleccione **ver código**.  
  
3. Agregar un `GetToolboxControl` método a la `MainWindow` clase que crea un <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, agrega un nuevo **cuadro de herramientas** categoría a la **cuadro de herramientas**y asigna el <xref:System.Activities.Statements.Assign> y <xref:System.Activities.Statements.Sequence> tipos de actividad en esa categoría.  
  
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
  
4. Agregar una privada `AddToolbox` método a la `MainWindow` clase que coloca el **cuadro de herramientas** en la columna izquierda de la cuadrícula.  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5. Agregue una llamada al método `AddToolBox` en el constructor de clase `MainWindow()` tal y como se muestra en el siguiente código.  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6. Presione F5 para compilar y ejecutar la solución. El **cuadro de herramientas** que contiene el <xref:System.Activities.Statements.Assign> y <xref:System.Activities.Statements.Sequence> se deben mostrar las actividades.  
  
### <a name="to-create-the-propertygrid"></a>Para crear PropertyGrid  
  
1. En el **el Explorador de soluciones** panel, haga clic en el archivo MainWindow.xaml y seleccione **ver código**.  
  
2. Agregar el `AddPropertyInspector` método a la `MainWindow` clase para colocar el **PropertyGrid** panel en la columna situada en la cuadrícula.  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3. Agregue una llamada al método `AddPropertyInspector` en el constructor de clase `MainWindow()` tal y como se muestra en el siguiente código.  
  
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
  
4. Presione F5 para compilar y ejecutar la solución. El **cuadro de herramientas**, lienzo de diseño de flujo de trabajo, y **PropertyGrid** paneles todos se deben mostrar y, cuando se arrastra un <xref:System.Activities.Statements.Assign> actividad o un <xref:System.Activities.Statements.Sequence> actividades al lienzo del diseño, el cuadrícula de propiedades debe actualizarse dependiendo de la actividad resaltada.  
  
## <a name="example"></a>Ejemplo  
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
  
## <a name="see-also"></a>Vea también

- [Rehospedaje del Diseñador de flujo de trabajo](rehosting-the-workflow-designer.md)
- [Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Tarea 2: Hospedar el Diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md)
