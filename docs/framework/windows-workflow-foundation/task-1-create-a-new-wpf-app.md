---
title: "Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89c929e71a2d64673f158f81c85d04c3443800ac
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="a8220-102">Tarea 1: Crear una nueva aplicación de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="a8220-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="a8220-103">En esta tarea, creará una aplicación [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] vacía usando para ello la plantilla de Visual Studio de aplicación WPF y agregará referencias a los ensamblados de flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] adecuados.</span><span class="sxs-lookup"><span data-stu-id="a8220-103">In this task, you will create an empty [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="a8220-104">Para crear el proyecto de aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="a8220-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="a8220-105">Abra [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] y en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a8220-105">Open [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="a8220-106">En el **nuevo proyecto** cuadro de diálogo, seleccione **Visual C#** o **Visual Basic** desde el **plantillas instaladas** panel en el lado izquierdo del el cuadro.</span><span class="sxs-lookup"><span data-stu-id="a8220-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="a8220-107">Si no aparece el idioma de su elección, mire debajo **otros lenguajes**.</span><span class="sxs-lookup"><span data-stu-id="a8220-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="a8220-108">Seleccione **Windows** en el **plantillas instaladas** panel.</span><span class="sxs-lookup"><span data-stu-id="a8220-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="a8220-109">En el panel superior, confirme que (el valor predeterminado) **.NET Framework 4** se ha seleccionado en el cuadro de lista desplegable y, a continuación, seleccione **aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="a8220-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="a8220-110">Establecer el nombre del proyecto para **HostingApplication** en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="a8220-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="a8220-111">Establece el nombre de la solución en **RehostingTheDesigner**.</span><span class="sxs-lookup"><span data-stu-id="a8220-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="a8220-112">Haga clic en **Aceptar** para crear el proyecto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8220-112">Click **OK** to create the application project.</span></span> [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]<span data-ttu-id="a8220-113"> crea una interfaz de usuario básica de WPF para su aplicación e incluye el XAML y los archivos de código subyacente adecuados.</span><span class="sxs-lookup"><span data-stu-id="a8220-113"> creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="a8220-114">Agregue referencias a **WorkflowModel** ensamblados.</span><span class="sxs-lookup"><span data-stu-id="a8220-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="a8220-115">Para ello, en **el Explorador de soluciones**, haga clic en el **HostingApplication** de proyecto y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="a8220-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="a8220-116">En el **Agregar referencia** cuadro de diálogo, haga clic en el **.NET** ficha, mantenga presionada la tecla CTRL, seleccione los ensamblados siguientes y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="a8220-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="a8220-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="a8220-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="a8220-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="a8220-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="a8220-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="a8220-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="a8220-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8220-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="a8220-121">Vea [tarea 2: hospedaje del Diseñador de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) para obtener información sobre cómo hospedar el lienzo de diseño del Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8220-121">See [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8220-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8220-122">See Also</span></span>  
 [<span data-ttu-id="a8220-123">Rehospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8220-123">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="a8220-124">Tarea 2: Hospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8220-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
