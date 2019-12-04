---
title: 'Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 29e50b24135cd3d6a02052d846e1781b0d9fa325
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716228"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid

En esta tarea, creará los paneles **cuadro de herramientas** y **PropertyGrid** y los agregará a la diseñador de flujo de trabajo de Windows hospedada en otro host.

Como referencia, al final de este tema se proporciona el código que debe estar en el archivo MainWindow.xaml.cs después de completar las tres tareas de la serie de temas de [rehospedamiento diseñador de flujo de trabajo](rehosting-the-workflow-designer.md) .

## <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>Para crear el Cuadro de herramientas y agregarlo a la cuadrícula

1. Abra el proyecto HostingApplication que obtuvo siguiendo el procedimiento descrito en [tarea 2: hospedar el diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md).

2. En el panel **Explorador de soluciones** , haga clic con el botón secundario en el archivo *MainWindow. Xaml* y seleccione **Ver código**.

3. Agregue un método `GetToolboxControl` a la clase `MainWindow` que crea un <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, agrega una nueva categoría de **cuadro de herramientas** al **cuadro de herramientas**y asigna los tipos de actividad <xref:System.Activities.Statements.Assign> y <xref:System.Activities.Statements.Sequence> a esa categoría.

    ```csharp
    private ToolboxControl GetToolboxControl()
    {
        // Create the ToolBoxControl.
        var ctrl = new ToolboxControl();

        // Create a category.
        var category = new ToolboxCategory("category1");

        // Create Toolbox items.
        var tool1 =
            new ToolboxItemWrapper("System.Activities.Statements.Assign",
            typeof(Assign).Assembly.FullName, null, "Assign");

        var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
            typeof(Sequence).Assembly.FullName, null, "Sequence");

        // Add the Toolbox items to the category.
        category.Add(tool1);
        category.Add(tool2);

        // Add the category to the ToolBox control.
        ctrl.Categories.Add(category);
        return ctrl;
    }
    ```

4. Agregue un método `AddToolbox` privado a la clase `MainWindow` que coloca el **cuadro de herramientas** en la columna izquierda de la cuadrícula.

    ```csharp
    private void AddToolBox()
    {
        ToolboxControl tc = GetToolboxControl();
        Grid.SetColumn(tc, 0);
        grid1.Children.Add(tc);
    }
    ```

5. Agregue una llamada al método `AddToolBox` en el constructor de la clase `MainWindow()` como se muestra en el código siguiente:

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();

        this.AddToolBox();
    }
    ```

6. Presione <kbd>F5</kbd> para compilar y ejecutar la solución. Se debe mostrar el **cuadro de herramientas** que contiene las actividades <xref:System.Activities.Statements.Assign> y <xref:System.Activities.Statements.Sequence>.

## <a name="to-create-the-propertygrid"></a>Para crear PropertyGrid

1. En el panel **Explorador de soluciones** , haga clic con el botón secundario en el archivo *MainWindow. Xaml* y seleccione **Ver código**.

2. Agregue el método `AddPropertyInspector` a la clase `MainWindow` para colocar el panel **PropertyGrid** en la columna situada más a la derecha en la cuadrícula:

    ```csharp
    private void AddPropertyInspector()
    {
        Grid.SetColumn(wd.PropertyInspectorView, 2);
        grid1.Children.Add(wd.PropertyInspectorView);
    }
    ```

3. Agregue una llamada al método `AddPropertyInspector` en el constructor de la clase `MainWindow()` como se muestra en el código siguiente:

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

4. Presione <kbd>F5</kbd> para compilar y ejecutar la solución. Se deben mostrar todos los paneles **cuadro de herramientas**, lienzo de diseño de flujo de trabajo y **PropertyGrid** , y al arrastrar una actividad <xref:System.Activities.Statements.Assign> o una actividad <xref:System.Activities.Statements.Sequence> al lienzo de diseño, la cuadrícula de propiedades debe actualizarse en función de la actividad resaltada.

## <a name="example"></a>Ejemplo

El archivo *MainWindow.Xaml.CS* debería contener ahora el siguiente código:

```csharp
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
// dlls added.
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
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }

        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }

        private ToolboxControl GetToolboxControl()
        {
            // Create the ToolBoxControl.
            var ctrl = new ToolboxControl();

            // Create a category.
            var category = new ToolboxCategory("category1");

            // Create Toolbox items.
            var tool1 =
                new ToolboxItemWrapper("System.Activities.Statements.Assign",
                typeof(Assign).Assembly.FullName, null, "Assign");

            var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
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
- [Tarea 1: Crear una aplicación de Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Tarea 2: Hospedaje del Diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md)
