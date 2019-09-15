---
title: 'Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 6339969c52a5c4eedfb0e89eebdc982ca3fe6686
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988710"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="8d57c-102">Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="8d57c-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>
<span data-ttu-id="8d57c-103">En esta tarea, creará los paneles **cuadro de herramientas** y **PropertyGrid** y los agregará a la hospedada en otro host [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d57c-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>  
  
 <span data-ttu-id="8d57c-104">Como referencia, al final de este tema se proporciona el código que debe estar en el archivo MainWindow.xaml.cs después de completar las tres tareas de la serie de temas de [rehospedamiento diseñador de flujo de trabajo](rehosting-the-workflow-designer.md) .</span><span class="sxs-lookup"><span data-stu-id="8d57c-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="8d57c-105">Para crear el Cuadro de herramientas y agregarlo a la cuadrícula</span><span class="sxs-lookup"><span data-stu-id="8d57c-105">To create the Toolbox and add it to the grid</span></span>  
  
1. <span data-ttu-id="8d57c-106">Abra el proyecto HostingApplication que obtuvo siguiendo el procedimiento descrito en [tarea 2: Hospede el Diseñador de flujo de trabajo](task-2-host-the-workflow-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8d57c-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md).</span></span>  
  
2. <span data-ttu-id="8d57c-107">En el panel **Explorador de soluciones** , haga clic con el botón secundario en el archivo MainWindow. XAML y seleccione **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="8d57c-107">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
3. <span data-ttu-id="8d57c-108">Agregue un `GetToolboxControl` método a la `MainWindow` clase que crea un <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, agrega una nueva categoría del **cuadro de herramientas** al **cuadro de herramientas**y asigna <xref:System.Activities.Statements.Assign> los <xref:System.Activities.Statements.Sequence> tipos de actividad y a esa categoría.</span><span class="sxs-lookup"><span data-stu-id="8d57c-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>  
  
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
  
4. <span data-ttu-id="8d57c-109">Agregue un método `AddToolbox` privado a la `MainWindow` clase que coloca el **cuadro de herramientas** en la columna izquierda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8d57c-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5. <span data-ttu-id="8d57c-110">Agregue una llamada al método `AddToolBox` en el constructor de clase `MainWindow()` tal y como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="8d57c-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6. <span data-ttu-id="8d57c-111">Presione F5 para compilar y ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="8d57c-111">Press F5 to build and run your solution.</span></span> <span data-ttu-id="8d57c-112">Se debe mostrar el <xref:System.Activities.Statements.Assign> cuadro <xref:System.Activities.Statements.Sequence> de **herramientas** que contiene las actividades y.</span><span class="sxs-lookup"><span data-stu-id="8d57c-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>  
  
### <a name="to-create-the-propertygrid"></a><span data-ttu-id="8d57c-113">Para crear PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="8d57c-113">To create the PropertyGrid</span></span>  
  
1. <span data-ttu-id="8d57c-114">En el panel **Explorador de soluciones** , haga clic con el botón secundario en el archivo MainWindow. XAML y seleccione **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="8d57c-114">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
2. <span data-ttu-id="8d57c-115">Agregue el `AddPropertyInspector` método a la `MainWindow` clase para colocar el panel **PropertyGrid** en la columna situada más a la derecha en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8d57c-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid.</span></span>  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3. <span data-ttu-id="8d57c-116">Agregue una llamada al método `AddPropertyInspector` en el constructor de clase `MainWindow()` tal y como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="8d57c-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
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
  
4. <span data-ttu-id="8d57c-117">Presione F5 para compilar y ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="8d57c-117">Press F5 to build and run the solution.</span></span> <span data-ttu-id="8d57c-118">Se deben mostrar todos los paneles **cuadro de herramientas**, lienzo de diseño de flujo de trabajo y **PropertyGrid** , <xref:System.Activities.Statements.Assign> y al arrastrar <xref:System.Activities.Statements.Sequence> una actividad o una actividad al lienzo de diseño, la cuadrícula de propiedades debe actualizarse en función del actividad resaltada.</span><span class="sxs-lookup"><span data-stu-id="8d57c-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d57c-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d57c-119">Example</span></span>  
 <span data-ttu-id="8d57c-120">El archivo MainWindow.xaml.cs debe contener ahora el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="8d57c-120">The MainWindow.xaml.cs file should now contain the following code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8d57c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d57c-121">See also</span></span>

- [<span data-ttu-id="8d57c-122">Rehospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="8d57c-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="8d57c-123">Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="8d57c-123">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="8d57c-124">Tarea 2: Hospede el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="8d57c-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
