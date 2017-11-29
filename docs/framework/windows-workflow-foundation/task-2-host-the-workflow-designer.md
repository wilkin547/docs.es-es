---
title: "Tarea 2: Hospedaje del Diseñador de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f3b35bf4150dc05c6bedaaebc65a0a188c5c782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="aba66-102">Tarea 2: Hospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="aba66-102">Task 2: Host the Workflow Designer</span></span>
<span data-ttu-id="aba66-103">En este tema se describe el procedimiento para hospedar una instancia de [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] en una aplicación [!INCLUDE[avalon1](../../../includes/avalon1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aba66-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application.</span></span>  
  
 <span data-ttu-id="aba66-104">El procedimiento se configura el **cuadrícula** control que contiene el diseñador, crea mediante programación una instancia de la <xref:System.Activities.Presentation.WorkflowDesigner> que contiene el valor predeterminado es <xref:System.Activities.Statements.Sequence> actividad, registra los metadatos del diseñador para proporcionar compatibilidad con el diseñador para integrados todas las actividades y hospeda el [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] en el [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="aba66-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] application.</span></span>  
  
### <a name="to-host-the-workflow-designer"></a><span data-ttu-id="aba66-105">Para hospedar el diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="aba66-105">To host the workflow designer</span></span>  
  
1.  <span data-ttu-id="aba66-106">Abra el HostingApplication proyecto que creó en [tarea 1: crear una nueva aplicación de Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md).</span><span class="sxs-lookup"><span data-stu-id="aba66-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md).</span></span>  
  
2.  <span data-ttu-id="aba66-107">Ajuste el tamaño de la ventana para facilitar el uso de [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aba66-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="aba66-108">Para ello, seleccione **MainWindow** en el diseñador, presione F4 para mostrar la **propiedades** ventana y, en la **diseño** sección, establezca el **ancho** a un valor de 600 y **alto** en un valor de 350.</span><span class="sxs-lookup"><span data-stu-id="aba66-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>  
  
3.  <span data-ttu-id="aba66-109">Establecer el nombre de la cuadrícula, seleccione el **cuadrícula** panel en el Diseñador de (haga clic en el cuadro dentro de la **MainWindow**) y estableciendo el **nombre** propiedad en la parte superior de la  **Propiedades** ventana en "grid1".</span><span class="sxs-lookup"><span data-stu-id="aba66-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>  
  
4.  <span data-ttu-id="aba66-110">En el **propiedades** ventana, haga clic en el botón de puntos suspensivos (**...** ) junto a la `ColumnDefinitions` propiedad para abrir el **Editor de la colección** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aba66-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="aba66-111">En el **Editor de la colección** cuadro de diálogo, haga clic en el **agregar** tres veces para insertar tres columnas en el diseño de botón.</span><span class="sxs-lookup"><span data-stu-id="aba66-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="aba66-112">La primera columna contendrá el **cuadro de herramientas**, la segunda columna va a hospedar la [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], y la tercera columna se utilizará para el inspector de propiedad.</span><span class="sxs-lookup"><span data-stu-id="aba66-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>  
  
6.  <span data-ttu-id="aba66-113">Establecer el `Width` propiedad de la columna central en el valor "4 *".</span><span class="sxs-lookup"><span data-stu-id="aba66-113">Set the `Width` property of the middle column to the value "4*".</span></span>  
  
7.  <span data-ttu-id="aba66-114">Haga clic en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="aba66-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="aba66-115">El siguiente XAML se agrega a su archivo MainWindow.xaml:</span><span class="sxs-lookup"><span data-stu-id="aba66-115">The following XAML is added to your MainWindow.xaml file:</span></span>  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8.  <span data-ttu-id="aba66-116">En **el Explorador de soluciones**, haga clic en MainWindow.xaml y seleccione **ver código**.</span><span class="sxs-lookup"><span data-stu-id="aba66-116">In **Solution Explorer**, right-click MainWindow.xaml and select **View Code**.</span></span> <span data-ttu-id="aba66-117">Modifique el código siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="aba66-117">Modify the code by following these steps:</span></span>  
  
    1.  <span data-ttu-id="aba66-118">Agregue los siguientes espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="aba66-118">Add the following namespaces:</span></span>  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  <span data-ttu-id="aba66-119">Para declarar un campo de miembro privado que hospede una instancia de <xref:System.Activities.Presentation.WorkflowDesigner>, agregue el siguiente código a la clase `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="aba66-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class.</span></span>  
  
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
  
    3.  <span data-ttu-id="aba66-120">Agregue el método `AddDesigner` siguiente a la clase `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="aba66-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="aba66-121">La implementación crea una instancia de la <xref:System.Activities.Presentation.WorkflowDesigner>, agrega un <xref:System.Activities.Statements.Sequence> actividad y lo coloca en la columna central de la grid1 **cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="aba66-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>  
  
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
  
    4.  <span data-ttu-id="aba66-122">Registre los metadatos del diseñador para agregar la compatibilidad con el diseñador para todas las actividades integradas.</span><span class="sxs-lookup"><span data-stu-id="aba66-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="aba66-123">Esto le permite colocar las actividades del cuadro de herramientas en la actividad <xref:System.Activities.Statements.Sequence> original en [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aba66-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="aba66-124">Para ello, agregue el método `RegisterMetadata` a la clase `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="aba66-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class.</span></span>  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="aba66-125">registrar los diseñadores de actividades, vea [Cómo: crear un diseñador de actividades personalizadas](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md).</span><span class="sxs-lookup"><span data-stu-id="aba66-125"> registering activity designers, see [How to: Create a Custom Activity Designer](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md).</span></span>  
  
    5.  <span data-ttu-id="aba66-126">En el constructor de clases `MainWindow`, agregue llamadas a los métodos declarados previamente para registrar los metadatos a fin de ser compatibles con el diseñador y crear <xref:System.Activities.Presentation.WorkflowDesigner>.</span><span class="sxs-lookup"><span data-stu-id="aba66-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>  
  
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
        >  <span data-ttu-id="aba66-127">El método `RegisterMetadata` registra los metadatos del diseñador de actividades integradas incluida la actividad <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="aba66-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="aba66-128">Puesto que el método `AddDesigner` usa la actividad <xref:System.Activities.Statements.Sequence>, es necesario llamar primero al método `RegisterMetadata`.</span><span class="sxs-lookup"><span data-stu-id="aba66-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>  
  
9. <span data-ttu-id="aba66-129">Presione F5 para compilar y ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="aba66-129">Press F5 to build and run the solution.</span></span>  
  
10. <span data-ttu-id="aba66-130">Vea [tarea 3: crear el cuadro de herramientas y paneles de PropertyGrid](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md) para obtener información sobre cómo agregar **cuadro de herramientas** y **PropertyGrid** admite su diseñador de flujo de trabajo rehospedado.</span><span class="sxs-lookup"><span data-stu-id="aba66-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba66-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="aba66-131">See Also</span></span>  
 [<span data-ttu-id="aba66-132">Rehospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="aba66-132">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="aba66-133">Tarea 1: Crear una aplicación de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="aba66-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
 [<span data-ttu-id="aba66-134">Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="aba66-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)
