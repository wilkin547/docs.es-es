---
title: Usar la actividad Interop en un flujo de trabajo de .NET Framework 4
ms.date: 03/30/2017
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
ms.openlocfilehash: 02eeaf5bb7ff484ba5982197fc395e247cd5a87f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528115"
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a><span data-ttu-id="eaa0c-102">Usar la actividad Interop en un flujo de trabajo de .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="eaa0c-102">Using the Interop Activity in a .NET Framework 4 Workflow</span></span>
<span data-ttu-id="eaa0c-103">Las actividades creadas con [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] o [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] pueden usarse en un flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] mediante la actividad <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-103">Activities created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] or [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] can be used in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow by using the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="eaa0c-104">En este tema se proporciona información general sobre el uso de la actividad <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-104">This topic provides an overview of using the <xref:System.Activities.Statements.Interop> activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eaa0c-105">El <xref:System.Activities.Statements.Interop> actividad no aparece en el cuadro de herramientas Diseñador de flujo de trabajo a menos que el proyecto del flujo de trabajo tiene su **.NET Framework de destino** configuración establecida en **.Net Framework 4** o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-105">The <xref:System.Activities.Statements.Interop> activity does not appear in the workflow designer toolbox unless the workflow's project has its **Target Framework** setting set to **.Net Framework 4** or later.</span></span>  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a><span data-ttu-id="eaa0c-106">Usar la actividad Interop en flujos de trabajo de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="eaa0c-106">Using the Interop Activity in .NET Framework 4.5 Workflows</span></span>  
 <span data-ttu-id="eaa0c-107">En este tema, se crea una biblioteca de actividades de [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] que contiene una actividad `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-107">In this topic, a [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity library is created that contains a `DiscountCalculator` activity.</span></span> <span data-ttu-id="eaa0c-108">`DiscountCalculator` calcula un descuento basado en el importe de una compra y consta de una clase <xref:System.Workflow.Activities.SequenceActivity> que contiene una <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-108">The `DiscountCalculator` calculates a discount based on a purchase amount and consists of a <xref:System.Workflow.Activities.SequenceActivity> that contains a <xref:System.Workflow.Activities.PolicyActivity>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eaa0c-109">La actividad de [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] creada en este tema usa <xref:System.Workflow.Activities.PolicyActivity> para implementar la lógica de la actividad.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-109">The [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity created in this topic uses a <xref:System.Workflow.Activities.PolicyActivity> to implement the logic of the activity.</span></span> <span data-ttu-id="eaa0c-110">No es necesario para usar una actividad [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] personalizada o la actividad <xref:System.Activities.Statements.Interop> a fin de usar reglas en un flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eaa0c-110">It is not required to use a custom [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity or the <xref:System.Activities.Statements.Interop> activity in order to use rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="eaa0c-111">Para obtener un ejemplo de uso de reglas en un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flujo de trabajo sin usar el <xref:System.Activities.Statements.Interop> actividad, consulte el [actividad Policy en .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-111">For an example of using rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow without using the <xref:System.Activities.Statements.Interop> activity, see the [Policy Activity in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) sample.</span></span>  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a><span data-ttu-id="eaa0c-112">Para crear el proyecto de la biblioteca de actividades de .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="eaa0c-112">To create the .NET Framework 3.5 activity library project</span></span>  
  
1.  <span data-ttu-id="eaa0c-113">Abra [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] y seleccione **New** y, a continuación, **proyecto...**</span><span class="sxs-lookup"><span data-stu-id="eaa0c-113">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New** and then **Project…**</span></span> <span data-ttu-id="eaa0c-114">desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-114">from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="eaa0c-115">Expanda el **otros tipos de proyectos** nodo en el **plantillas instaladas** panel y seleccione **soluciones de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-115">Expand the **Other Project Types** node in the **Installed Templates** pane and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="eaa0c-116">Seleccione **solución en blanco** desde el **soluciones de Visual Studio** lista.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-116">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="eaa0c-117">Tipo `PolicyInteropDemo` en el **nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-117">Type `PolicyInteropDemo` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="eaa0c-118">Haga clic en **PolicyInteropDemo** en **el Explorador de soluciones** y seleccione **agregar** y, a continuación, **nuevo proyecto...** .</span><span class="sxs-lookup"><span data-stu-id="eaa0c-118">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add** and then **New Project…**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="eaa0c-119">Si el **el Explorador de soluciones** ventana no está visible, seleccione **el Explorador de soluciones** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-119">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="eaa0c-120">En el **plantillas instaladas** lista, seleccione **Visual C#** y, a continuación, **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-120">In the **Installed Templates** list, select **Visual C#** and then **Workflow**.</span></span> <span data-ttu-id="eaa0c-121">Seleccione **.NET Framework 3.5** desde la lista desplegable de versión de .NET Framework y, a continuación, seleccione **Workflow Activity Library** desde el **plantillas** lista.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-121">Select **.NET Framework 3.5** from the .NET Framework version drop-down list, and then select **Workflow Activity Library** from the **Templates** list.</span></span>  
  
6.  <span data-ttu-id="eaa0c-122">Tipo `PolicyActivityLibrary` en el **nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-122">Type `PolicyActivityLibrary` in the **Name** box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="eaa0c-123">Haga clic en **Activity1.cs** en **el Explorador de soluciones** y seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-123">Right-click **Activity1.cs** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="eaa0c-124">Haga clic en **Aceptar** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-124">Click **OK** to confirm.</span></span>  
  
#### <a name="to-create-the-discountcalculator-activity"></a><span data-ttu-id="eaa0c-125">Para crear la actividad DiscountCalculator</span><span class="sxs-lookup"><span data-stu-id="eaa0c-125">To create the DiscountCalculator activity</span></span>  
  
1.  <span data-ttu-id="eaa0c-126">Haga clic en **PolicyActivityLibrary** en **el Explorador de soluciones** y seleccione **agregar** y, a continuación, **actividad...** .</span><span class="sxs-lookup"><span data-stu-id="eaa0c-126">Right-click **PolicyActivityLibrary** in **Solution Explorer** and select **Add** and then **Activity…**.</span></span>  
  
2.  <span data-ttu-id="eaa0c-127">Seleccione **Activity (con separación de código)** desde el **elementos de Visual C#** lista.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-127">Select **Activity (with code separation)** from the **Visual C# Items** list.</span></span> <span data-ttu-id="eaa0c-128">Tipo `DiscountCalculator` en el **nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-128">Type `DiscountCalculator` in the **Name** box and click **OK**.</span></span>  
  
3.  <span data-ttu-id="eaa0c-129">Haga clic en **DiscountCalculator.xoml** en **el Explorador de soluciones** y seleccione **ver código**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-129">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Code**.</span></span>  
  
4.  <span data-ttu-id="eaa0c-130">Agregue las siguientes propiedades a la clase `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-130">Add the following three properties to the `DiscountCalculator` class.</span></span>  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  <span data-ttu-id="eaa0c-131">Haga clic en **DiscountCalculator.xoml** en **el Explorador de soluciones** y seleccione **Diseñador de vistas**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-131">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Designer**.</span></span>  
  
6.  <span data-ttu-id="eaa0c-132">Arrastre un **directiva** actividad desde la **Windows Workflow v3.0** sección de la **cuadro de herramientas** y colóquelo el **DiscountCalculator** actividad .</span><span class="sxs-lookup"><span data-stu-id="eaa0c-132">Drag a **Policy** activity from the **Windows Workflow v3.0** section of the **Toolbox** and drop it in the **DiscountCalculator** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="eaa0c-133">Si el **cuadro de herramientas** ventana no está visible, seleccione **cuadro de herramientas** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-133">If the **Toolbox** window is not visible, select **Toolbox** from the **View** menu.</span></span>  
  
#### <a name="to-configure-the-rules"></a><span data-ttu-id="eaa0c-134">Para configurar las reglas</span><span class="sxs-lookup"><span data-stu-id="eaa0c-134">To configure the rules</span></span>  
  
1.  <span data-ttu-id="eaa0c-135">Haga clic en la recién agregada **directiva** actividad para seleccionarlo y, si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-135">Click the newly added **Policy** activity to select it, if it is not already selected.</span></span>  
  
2.  <span data-ttu-id="eaa0c-136">Haga clic en el **RuleSetReference** propiedad en el **propiedades** ventana para seleccionarlo y haga clic en el botón de puntos suspensivos a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-136">Click the **RuleSetReference** property in the **Properties** window to select it, and click the ellipsis button to the right of the property.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="eaa0c-137">Si el **propiedades** ventana no está visible, elija **ventana propiedades** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-137">If the **Properties** window is not visible, choose **Properties Window** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="eaa0c-138">Seleccione **haga clic en nuevo...** .</span><span class="sxs-lookup"><span data-stu-id="eaa0c-138">Select **Click New…**.</span></span>  
  
4.  <span data-ttu-id="eaa0c-139">Haga clic en **Agregar regla**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-139">Click **Add Rule**.</span></span>  
  
5.  <span data-ttu-id="eaa0c-140">Escriba la siguiente expresión en el **condición** cuadro.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-140">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  <span data-ttu-id="eaa0c-141">Escriba la siguiente expresión en el **acciones Then** cuadro.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-141">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  <span data-ttu-id="eaa0c-142">Haga clic en **Agregar regla**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-142">Click **Add Rule**.</span></span>  
  
8.  <span data-ttu-id="eaa0c-143">Escriba la siguiente expresión en el **condición** cuadro.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-143">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. <span data-ttu-id="eaa0c-144">Escriba la siguiente expresión en el **acciones Then** cuadro.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-144">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. <span data-ttu-id="eaa0c-145">Haga clic en **Agregar regla**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-145">Click **Add Rule**.</span></span>  
  
11. <span data-ttu-id="eaa0c-146">Escriba la siguiente expresión en el **condición** cuadro.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-146">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. <span data-ttu-id="eaa0c-147">Escriba la siguiente expresión en el **acciones Then** cuadro.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-147">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. <span data-ttu-id="eaa0c-148">Escriba la siguiente expresión en el **acciones Else** cuadro.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-148">Type the following expression into the **Else Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. <span data-ttu-id="eaa0c-149">Haga clic en **Aceptar** para cerrar el **Editor de conjunto de reglas** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-149">Click **OK** to close the **Rule Set Editor** dialog box.</span></span>  
  
15. <span data-ttu-id="eaa0c-150">Asegúrese de que el recién creado <xref:System.Workflow.Activities.Rules.RuleSet> está seleccionado en el **nombre** lista y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-150">Ensure that the newly-created <xref:System.Workflow.Activities.Rules.RuleSet> is selected in the **Name** list, and click **OK**.</span></span>  
  
16. <span data-ttu-id="eaa0c-151">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-151">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
 <span data-ttu-id="eaa0c-152">Las reglas agregadas a la actividad `DiscountCalculator` en este procedimiento se muestran en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-152">The rules added to the `DiscountCalculator` activity in this procedure are shown in the following code example.</span></span>  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 <span data-ttu-id="eaa0c-153">Cuando <xref:System.Workflow.Activities.PolicyActivity> se ejecuta, estas tres reglas evalúan y modifican los valores de propiedad `Subtotal`, `DiscountPercent` y `Total`de la actividad `DiscountCalculator` para calcular el descuento deseado.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-153">When the <xref:System.Workflow.Activities.PolicyActivity> executes, these three rules evaluate and modify the `Subtotal`, `DiscountPercent`, and `Total` property values of the `DiscountCalculator` activity to calculate the desired discount.</span></span>  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a><span data-ttu-id="eaa0c-154">Usar la actividad DiscountCalculator con la actividad Interop</span><span class="sxs-lookup"><span data-stu-id="eaa0c-154">Using the DiscountCalculator Activity with the Interop Activity</span></span>  
 <span data-ttu-id="eaa0c-155">Para usar la actividad `DiscountCalculator` dentro del flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], se usará la actividad <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-155">To use the `DiscountCalculator` activity inside a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow, the <xref:System.Activities.Statements.Interop> activity is used.</span></span> <span data-ttu-id="eaa0c-156">En esta sección se crean dos flujos de trabajo, uno que usa código y otro que usa diseñador de flujo de trabajo, que a su vez muestran cómo usar la actividad <xref:System.Activities.Statements.Interop> con la actividad `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-156">In this section two workflows are created, one using code and one using the workflow designer, which show how to use the <xref:System.Activities.Statements.Interop> activity with the `DiscountCalculator` activity.</span></span> <span data-ttu-id="eaa0c-157">La misma aplicación host se usa para ambos flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-157">The same host application is used for both workflows.</span></span>  
  
#### <a name="to-create-the-host-application"></a><span data-ttu-id="eaa0c-158">Para crear la aplicación host</span><span class="sxs-lookup"><span data-stu-id="eaa0c-158">To create the host application</span></span>  
  
1.  <span data-ttu-id="eaa0c-159">Haga clic en **PolicyInteropDemo** en **el Explorador de soluciones** y seleccione **agregar**y, a continuación, **nuevo proyecto...** .</span><span class="sxs-lookup"><span data-stu-id="eaa0c-159">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add**, and then **New Project…**.</span></span>  
  
2.  <span data-ttu-id="eaa0c-160">Asegúrese de que **.NET Framework 4.5** está seleccionado en la lista desplegable de versión de .NET Framework y seleccione **aplicación de consola de flujos de trabajo** desde el **elementos de Visual C#** lista.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-160">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list, and select  **Workflow Console Application** from the **Visual C# Items** list.</span></span>  
  
3.  <span data-ttu-id="eaa0c-161">Tipo `PolicyInteropHost` en el **nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-161">Type `PolicyInteropHost` into the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="eaa0c-162">Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-162">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="eaa0c-163">En el **.NET framework de destino** desplegable lista, cambie la selección de **.NET Framework 4 Client Profile** a **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-163">In the **Target framework** drop-down list, change the selection from **.NET Framework 4 Client Profile** to **.NET Framework 4.5**.</span></span> <span data-ttu-id="eaa0c-164">Haga clic en **Sí** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-164">Click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="eaa0c-165">Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **Agregar referencia...** .</span><span class="sxs-lookup"><span data-stu-id="eaa0c-165">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
7.  <span data-ttu-id="eaa0c-166">Seleccione **PolicyActivityLibrary** desde el **proyectos** ficha y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-166">Select **PolicyActivityLibrary** from the **Projects** tab and click **OK**.</span></span>  
  
8.  <span data-ttu-id="eaa0c-167">Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **Agregar referencia...** .</span><span class="sxs-lookup"><span data-stu-id="eaa0c-167">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
9. <span data-ttu-id="eaa0c-168">Seleccione **System.Workflow.Activities**, **System.Workflow.ComponentModel**y, a continuación, **System.Workflow.Runtime** desde el **.NET**ficha y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-168">Select **System.Workflow.Activities**, **System.Workflow.ComponentModel**, and then **System.Workflow.Runtime** from the **.NET** tab and click **OK**.</span></span>  
  
10. <span data-ttu-id="eaa0c-169">Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-169">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>  
  
11. <span data-ttu-id="eaa0c-170">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="using-the-interop-activity-in-code"></a><span data-ttu-id="eaa0c-171">Usar la actividad Interop en el código</span><span class="sxs-lookup"><span data-stu-id="eaa0c-171">Using the Interop Activity in Code</span></span>  
 <span data-ttu-id="eaa0c-172">En este ejemplo, se crea una definición de flujo de trabajo mediante el código que contiene las actividades <xref:System.Activities.Statements.Interop> y `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-172">In this example, a workflow definition is created using code that contains the <xref:System.Activities.Statements.Interop> activity and the `DiscountCalculator` activity.</span></span> <span data-ttu-id="eaa0c-173">Este flujo de trabajo se invoca usando <xref:System.Activities.WorkflowInvoker> y los resultados de la evaluación de la regla se escriben en la consola mediante una actividad <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-173">This workflow is invoked using <xref:System.Activities.WorkflowInvoker> and the results of the rule evaluation are written to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
##### <a name="to-use-the-interop-activity-in-code"></a><span data-ttu-id="eaa0c-174">Para usar la actividad Interop en código</span><span class="sxs-lookup"><span data-stu-id="eaa0c-174">To use the Interop activity in code</span></span>  
  
1.  <span data-ttu-id="eaa0c-175">Haga clic en **Program.cs** en **el Explorador de soluciones** y seleccione **ver código**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-175">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="eaa0c-176">Agregue la instrucción `using` siguiente en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-176">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  <span data-ttu-id="eaa0c-177">Quite el contenido del método `Main` y sustitúyalo con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="eaa0c-177">Remove the contents of the `Main` method and replace with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  <span data-ttu-id="eaa0c-178">Cree un nuevo método en la clase `Program` denominada `CalculateDiscountUsingCodeWorkflow` que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-178">Create a new method in the `Program` class called `CalculateDiscountUsingCodeWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="eaa0c-179">Las propiedades `Subtotal`, `DiscountPercent` y `Total` de la actividad `DiscountCalculator` se producen como argumentos de la actividad <xref:System.Activities.Statements.Interop>, y se enlazan a variables locales del flujo de trabajo de la colección <xref:System.Activities.Statements.Interop> de la actividad <xref:System.Activities.Statements.Interop.ActivityProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-179">The `Subtotal`, `DiscountPercent`, and `Total` properties of the `DiscountCalculator` activity are surfaced as arguments of the <xref:System.Activities.Statements.Interop> activity, and bound to local workflow variables in the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityProperties%2A> collection.</span></span> <span data-ttu-id="eaa0c-180">`Subtotal` se agrega como argumento <xref:System.Activities.ArgumentDirection.In> porque los datos de `Subtotal` fluyen hacia la actividad <xref:System.Activities.Statements.Interop>, y `DiscountPercent` y `Total` se agregan como argumentos <xref:System.Activities.ArgumentDirection.Out> porque sus datos fluyen fuera de la actividad <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-180">`Subtotal` is added as an <xref:System.Activities.ArgumentDirection.In> argument because the `Subtotal` data flows into the <xref:System.Activities.Statements.Interop> activity, and `DiscountPercent` and `Total` are added as <xref:System.Activities.ArgumentDirection.Out> arguments because their data flows out of the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="eaa0c-181">Tenga en cuenta que se agregan los dos argumentos <xref:System.Activities.ArgumentDirection.Out> con los nombres `DiscountPercentOut` y `TotalOut` para indicar que representan argumentos <xref:System.Activities.ArgumentDirection.Out>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-181">Note that the two <xref:System.Activities.ArgumentDirection.Out> arguments are added with the names `DiscountPercentOut` and `TotalOut` to indicate that they represent <xref:System.Activities.ArgumentDirection.Out> arguments.</span></span> <span data-ttu-id="eaa0c-182">El tipo `DiscountCalculator` se especifica como <xref:System.Activities.Statements.Interop> de la actividad <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-182">The `DiscountCalculator` type is specified as the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span></span>  
  
5.  <span data-ttu-id="eaa0c-183">Presione CTRL+F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-183">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="eaa0c-184">Sustituya los valores diferentes para que el valor `Subtotal` pruebe los niveles del descuento diferentes proporcionados por la actividad `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-184">Substitute different values for the `Subtotal` value to test out the different discount levels provided by the `DiscountCalculator` activity.</span></span>  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a><span data-ttu-id="eaa0c-185">Usar la actividad Interop en el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="eaa0c-185">Using the Interop Activity in the Workflow Designer</span></span>  
 <span data-ttu-id="eaa0c-186">En este ejemplo, use crea un flujo de trabajo con el diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-186">In this example, a workflow is created using the workflow designer.</span></span> <span data-ttu-id="eaa0c-187">Este flujo de trabajo tiene la misma funcionalidad que el ejemplo anterior, excepto que en lugar de usar una actividad <xref:System.Activities.Statements.WriteLine> para mostrar el descuento, la aplicación host recupera y muestra la información del descuento cuando el flujo de trabajo se completa.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-187">This workflow has the same functionality as the previous example, except than instead of using a <xref:System.Activities.Statements.WriteLine> activity to display the discount, the host application retrieves and displays the discount information when the workflow completes.</span></span> <span data-ttu-id="eaa0c-188">Asimismo, en lugar de usar las variables de flujo de trabajo locales para contener los datos, los argumentos se crean en el diseñador de flujo de trabajo y los valores se pasan desde el host cuando se invoca el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-188">Also, instead of using local workflow variables to contain the data, arguments are created in the workflow designer and the values are passed in from the host when the workflow is invoked.</span></span>  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a><span data-ttu-id="eaa0c-189">Para hospedar PolicyActivity usando un flujo de trabajo creado por el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="eaa0c-189">To host the PolicyActivity using a Workflow Designer-created workflow</span></span>  
  
1.  <span data-ttu-id="eaa0c-190">Haga clic en **Workflow1.xaml** en **el Explorador de soluciones** y seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-190">Right-click **Workflow1.xaml** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="eaa0c-191">Haga clic en **Aceptar** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-191">Click **OK** to confirm.</span></span>  
  
2.  <span data-ttu-id="eaa0c-192">Haga clic en **PolicyInteropHost** en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="eaa0c-192">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add**, **New Item…**.</span></span>  
  
3.  <span data-ttu-id="eaa0c-193">Expanda el **elementos de Visual C#** nodo y seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-193">Expand the **Visual C# Items** node and select **Workflow**.</span></span> <span data-ttu-id="eaa0c-194">Seleccione **actividad** desde el **elementos de Visual C#** lista.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-194">Select **Activity** from the **Visual C# Items** list.</span></span>  
  
4.  <span data-ttu-id="eaa0c-195">Tipo `DiscountWorkflow` en el **nombre** y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-195">Type `DiscountWorkflow` into the **Name** box and click **Add**.</span></span>  
  
5.  <span data-ttu-id="eaa0c-196">Haga clic en el **argumentos** botón en la parte inferior izquierda del Diseñador de flujo de trabajo para mostrar el **argumentos** panel.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-196">Click the **Arguments** button on the lower left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
6.  <span data-ttu-id="eaa0c-197">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-197">Click **Create Argument**.</span></span>  
  
7.  <span data-ttu-id="eaa0c-198">Tipo `Subtotal` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **doble** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-198">Type `Subtotal` into the **Name** box, select **In** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eaa0c-199">Si **doble** no está en el **tipo de argumento** lista desplegable, seleccione **buscar tipos...** , tipo `System.Double` en el **nombre de tipo** cuadro y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-199">If **Double** is not in the **Argument type** drop-down list, select **Browse for Types …**, type `System.Double` in the **Type Name** box, and click **OK**.</span></span>  
  
8.  <span data-ttu-id="eaa0c-200">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-200">Click **Create Argument**.</span></span>  
  
9. <span data-ttu-id="eaa0c-201">Tipo `DiscountPercent` en el **nombre** cuadro, seleccione **Out** desde el **dirección** lista desplegable, seleccione **doble** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-201">Type `DiscountPercent` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
10. <span data-ttu-id="eaa0c-202">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-202">Click **Create Argument**.</span></span>  
  
11. <span data-ttu-id="eaa0c-203">Tipo `Total` en el **nombre** cuadro, seleccione **Out** desde el **dirección** lista desplegable, seleccione **doble** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-203">Type `Total` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
12. <span data-ttu-id="eaa0c-204">Haga clic en el **argumentos** botón en la parte inferior izquierda del Diseñador de flujo de trabajo para cerrar el **argumentos** panel.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-204">Click the **Arguments** button on the lower left side of the workflow designer to close the **Arguments** pane.</span></span>  
  
13. <span data-ttu-id="eaa0c-205">Arrastre un **secuencia** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquela en la superficie del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-205">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the workflow designer surface.</span></span>  
  
14. <span data-ttu-id="eaa0c-206">Arrastre un **interoperabilidad** actividad desde la **migración** sección de la **cuadro de herramientas** y colóquelo el **secuencia** actividad.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-206">Drag an **Interop** activity from the **Migration** section of the **Toolbox** and drop it in the **Sequence** activity.</span></span>  
  
15. <span data-ttu-id="eaa0c-207">Haga clic en el **interoperabilidad** actividad en el **haga clic aquí para examinar...**</span><span class="sxs-lookup"><span data-stu-id="eaa0c-207">Click the **Interop** activity on the **Click to browse…**</span></span> <span data-ttu-id="eaa0c-208">etiqueta, escriba **DiscountCalculator** en el **nombre de tipo** cuadro y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-208">label, type **DiscountCalculator** in the **Type Name** box, and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eaa0c-209">Cuando la actividad <xref:System.Activities.Statements.Interop> se agrega al flujo de trabajo y el tipo `DiscountCalculator` se especifica como su <xref:System.Activities.Statements.Interop.ActivityType%2A>, la actividad <xref:System.Activities.Statements.Interop> expone tres argumentos <xref:System.Activities.ArgumentDirection.In> y tres argumentos <xref:System.Activities.ArgumentDirection.Out> que representan las tres propiedades públicas de la actividad `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-209">When the <xref:System.Activities.Statements.Interop> activity is added to the workflow and the `DiscountCalculator` type is specified as its <xref:System.Activities.Statements.Interop.ActivityType%2A>, the <xref:System.Activities.Statements.Interop> activity exposes three <xref:System.Activities.ArgumentDirection.In> arguments and three <xref:System.Activities.ArgumentDirection.Out> arguments that represent the three public properties of the `DiscountCalculator` activity.</span></span> <span data-ttu-id="eaa0c-210">El <xref:System.Activities.ArgumentDirection.In> argumentos tienen el mismo nombre que las tres propiedades públicas y los tres <xref:System.Activities.ArgumentDirection.Out> argumentos tengan los mismos nombres con **Out** anexado al nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-210">The <xref:System.Activities.ArgumentDirection.In> arguments have the same name as the three public properties, and the three <xref:System.Activities.ArgumentDirection.Out> arguments have the same names with **Out** appended to the property name.</span></span> <span data-ttu-id="eaa0c-211">En los siguientes pasos, los argumentos de flujo de trabajo creados en los pasos anteriores se enlazan a los argumentos de la actividad <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-211">In the following steps, the workflow arguments created in the previous steps are bound to the <xref:System.Activities.Statements.Interop> activity’s arguments.</span></span>  
  
16. <span data-ttu-id="eaa0c-212">Tipo `DiscountPercent` en el **escriba una expresión de VB** cuadro a la derecha de la **DiscountPercentOut** propiedad y presione TAB.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-212">Type `DiscountPercent` into the **Enter a VB expression** box to the right of the **DiscountPercentOut** property and press TAB.</span></span>  
  
17. <span data-ttu-id="eaa0c-213">Tipo `Subtotal` en el **escriba una expresión de VB** cuadro a la derecha de la **Subtotal** propiedad y presione TAB.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-213">Type `Subtotal` into the **Enter a VB expression** box to the right of the **Subtotal** property and press TAB.</span></span>  
  
18. <span data-ttu-id="eaa0c-214">Tipo `Total` en el **escriba una expresión de VB** cuadro a la derecha de la **TotalOut** propiedad y presione TAB.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-214">Type `Total` into the **Enter a VB expression** box to the right of the **TotalOut** property and press TAB.</span></span>  
  
19. <span data-ttu-id="eaa0c-215">Haga clic en **Program.cs** en **el Explorador de soluciones** y seleccione **ver código**.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-215">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
20. <span data-ttu-id="eaa0c-216">Agregue la instrucción `using` siguiente en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-216">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. <span data-ttu-id="eaa0c-217">Ponga un comentario sobre la llamada al método `CalculateDiscountInCode` en el método `Main` y agregue el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-217">Comment out the call to the `CalculateDiscountInCode` method in the `Main` method and add the following code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eaa0c-218">Si no siguiera el procedimiento anterior y el código `Main` predeterminado estuviera presente, reemplace el contenido de `Main` con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-218">If you did not follow the previous procedure and the default `Main` code is present, replace the contents of `Main` with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. <span data-ttu-id="eaa0c-219">Cree un nuevo método en la clase `Program` denominada `CalculateDiscountUsingDesignerWorkflow` que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-219">Create a new method in the `Program` class called `CalculateDiscountUsingDesignerWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. <span data-ttu-id="eaa0c-220">Presione CTRL+F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-220">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="eaa0c-221">Para especificar un importe de `Subtotal` distinto, cambie el valor de `SubtotalValue` en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-221">To specify a different `Subtotal` amount, change the value of `SubtotalValue` in the following code.</span></span>  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a><span data-ttu-id="eaa0c-222">Información general de las características de las reglas</span><span class="sxs-lookup"><span data-stu-id="eaa0c-222">Rules Features Overview</span></span>  
 <span data-ttu-id="eaa0c-223">El motor de reglas de [!INCLUDE[wf1](../../../includes/wf1-md.md)] proporciona soporte técnico para procesar reglas según la prioridad con soporte para el encadenamiento delantero.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-223">The [!INCLUDE[wf1](../../../includes/wf1-md.md)] rules engine provides support for processing rules in a priority-based manner with support for forward chaining.</span></span> <span data-ttu-id="eaa0c-224">Las reglas se pueden evaluar para un elemento único o para los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-224">Rules can be evaluated for a single item or for items in a collection.</span></span> <span data-ttu-id="eaa0c-225">Para ver una información general de reglas e información sobre la funcionalidad específica de reglas, consulte la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-225">For an overview of rules and information on specific rules functionality, please refer to the following table.</span></span>  
  
|<span data-ttu-id="eaa0c-226">Característica de reglas</span><span class="sxs-lookup"><span data-stu-id="eaa0c-226">Rules Feature</span></span>|<span data-ttu-id="eaa0c-227">Documentación</span><span class="sxs-lookup"><span data-stu-id="eaa0c-227">Documentation</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="eaa0c-228">Información general sobre reglas</span><span class="sxs-lookup"><span data-stu-id="eaa0c-228">Rules Overview</span></span>|[<span data-ttu-id="eaa0c-229">Introducción al motor de reglas de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="eaa0c-229">Introduction to the Windows Workflow Foundation Rules Engine</span></span>](https://go.microsoft.com/fwlink/?LinkID=152836)|  
|<span data-ttu-id="eaa0c-230">RuleSet</span><span class="sxs-lookup"><span data-stu-id="eaa0c-230">RuleSet</span></span>|<span data-ttu-id="eaa0c-231">[Utilización de RuleSets en flujos de trabajo](https://go.microsoft.com/fwlink/?LinkId=178516) y <xref:System.Workflow.Activities.Rules.RuleSet></span><span class="sxs-lookup"><span data-stu-id="eaa0c-231">[Using RuleSets in Workflows](https://go.microsoft.com/fwlink/?LinkId=178516) and <xref:System.Workflow.Activities.Rules.RuleSet></span></span>|  
|<span data-ttu-id="eaa0c-232">Evaluación de reglas</span><span class="sxs-lookup"><span data-stu-id="eaa0c-232">Evaluation of Rules</span></span>|[<span data-ttu-id="eaa0c-233">Evaluación de reglas en RuleSets</span><span class="sxs-lookup"><span data-stu-id="eaa0c-233">Rules Evaluation in RuleSets</span></span>](https://go.microsoft.com/fwlink/?LinkId=178517)|  
|<span data-ttu-id="eaa0c-234">Encadenamiento de reglas</span><span class="sxs-lookup"><span data-stu-id="eaa0c-234">Rules Chaining</span></span>|<span data-ttu-id="eaa0c-235">[Control de encadenamiento](https://go.microsoft.com/fwlink/?LinkId=178518) y [encadenamiento delantero de reglas](https://go.microsoft.com/fwlink/?LinkId=178519)</span><span class="sxs-lookup"><span data-stu-id="eaa0c-235">[Forward Chaining Control](https://go.microsoft.com/fwlink/?LinkId=178518) and [Forward Chaining of Rules](https://go.microsoft.com/fwlink/?LinkId=178519)</span></span>|  
|<span data-ttu-id="eaa0c-236">Procesamiento de colecciones en reglas</span><span class="sxs-lookup"><span data-stu-id="eaa0c-236">Processing Collections in Rules</span></span>|[<span data-ttu-id="eaa0c-237">Procesamiento de colecciones en reglas</span><span class="sxs-lookup"><span data-stu-id="eaa0c-237">Processing Collections in Rules</span></span>](https://go.microsoft.com/fwlink/?LinkId=178520)|  
|<span data-ttu-id="eaa0c-238">Usar PolicyActivity</span><span class="sxs-lookup"><span data-stu-id="eaa0c-238">Using the PolicyActivity</span></span>|<span data-ttu-id="eaa0c-239">[Uso de la actividad PolicyActivity](https://go.microsoft.com/fwlink/?LinkId=178521) y <xref:System.Workflow.Activities.PolicyActivity></span><span class="sxs-lookup"><span data-stu-id="eaa0c-239">[Using the PolicyActivity Activity](https://go.microsoft.com/fwlink/?LinkId=178521) and <xref:System.Workflow.Activities.PolicyActivity></span></span>|  
  
 <span data-ttu-id="eaa0c-240">Los flujos de trabajo creados en [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] no usan todas las características de reglas proporcionadas por [!INCLUDE[wf1](../../../includes/wf1-md.md)], como las condiciones de actividad declarativas y las actividades condicionales como, por ejemplo, <xref:System.Workflow.Activities.ConditionedActivityGroup> y <xref:System.Workflow.Activities.ReplicatorActivity>.</span><span class="sxs-lookup"><span data-stu-id="eaa0c-240">Workflows created in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] do not use all of the rules features provided by [!INCLUDE[wf1](../../../includes/wf1-md.md)], such as declarative activity conditions and conditional activities such as the <xref:System.Workflow.Activities.ConditionedActivityGroup> and <xref:System.Workflow.Activities.ReplicatorActivity>.</span></span> <span data-ttu-id="eaa0c-241">Si es necesario, esta funcionalidad está disponible para flujos de trabajo creados con [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] y [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eaa0c-241">If required, this functionality is available for workflows created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="eaa0c-242">Para obtener más información, consulte [Guía de migración](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="eaa0c-242">For more information, see [Migration Guidance](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>
