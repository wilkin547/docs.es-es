---
title: 'Tarea 1: Crear una aplicación de Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 3205840da575041b449eb841fc8084e89937fca7
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031896"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="11d63-102">Tarea 1: Crear una aplicación de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="11d63-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>

<span data-ttu-id="11d63-103">En esta tarea, creará una aplicación de Windows Presentation Foundation (WPF) vacía mediante la plantilla de Visual Studio de aplicación WPF y agregará referencias a los ensamblados de flujo de trabajo [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] apropiados.</span><span class="sxs-lookup"><span data-stu-id="11d63-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
## <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="11d63-104">Para crear el proyecto de aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="11d63-104">To create the WPF Application project</span></span>

1. <span data-ttu-id="11d63-105">Abra Visual Studio y, en el menú **archivo** , seleccione **nuevo**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="11d63-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="11d63-106">En el cuadro de diálogo **nuevo proyecto** , seleccione **Visual C#**  o **Visual Basic** en el panel **plantillas instaladas** en el lado izquierdo del cuadro.</span><span class="sxs-lookup"><span data-stu-id="11d63-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="11d63-107">Si el idioma de su elección no aparece, mire debajo de **otros idiomas**.</span><span class="sxs-lookup"><span data-stu-id="11d63-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>

3. <span data-ttu-id="11d63-108">Seleccione **Windows** en el panel **plantillas instaladas** .</span><span class="sxs-lookup"><span data-stu-id="11d63-108">Select **Windows** in the **Installed Templates** pane.</span></span>

4. <span data-ttu-id="11d63-109">En el panel superior, confirme que se ha seleccionado (el valor predeterminado) **.NET Framework 4** en el cuadro de lista desplegable y, a continuación, seleccione **aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="11d63-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>

5. <span data-ttu-id="11d63-110">Establezca el nombre del proyecto en **HostingApplication** en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="11d63-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>

6. <span data-ttu-id="11d63-111">Establezca el nombre de la solución en **RehostingTheDesigner**.</span><span class="sxs-lookup"><span data-stu-id="11d63-111">Set the solution name to **RehostingTheDesigner**.</span></span>

7. <span data-ttu-id="11d63-112">Haga clic en **Aceptar** para crear el proyecto de aplicación.</span><span class="sxs-lookup"><span data-stu-id="11d63-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="11d63-113">Visual Studio crea una interfaz de usuario de WPF básica para su aplicación e incluye los archivos XAML y de código subyacente adecuados.</span><span class="sxs-lookup"><span data-stu-id="11d63-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>

8. <span data-ttu-id="11d63-114">Agregue referencias a los ensamblados de **WorkflowModel** .</span><span class="sxs-lookup"><span data-stu-id="11d63-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="11d63-115">Para ello, en **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **HostingApplication** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="11d63-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>

9. <span data-ttu-id="11d63-116">En el cuadro de diálogo **Agregar referencia** , haga clic en la pestaña **.net** , mantenga presionada la tecla Ctrl, seleccione los siguientes ensamblados y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="11d63-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>

    - <span data-ttu-id="11d63-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="11d63-117">System.Activities</span></span>
    - <span data-ttu-id="11d63-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="11d63-118">System.Activities.Presentation</span></span>
    - <span data-ttu-id="11d63-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="11d63-119">System.Activities.Core.Presentation</span></span>

10. <span data-ttu-id="11d63-120">Consulte @no__t 0Task 2: Hospede el Diseñador de flujo de trabajo @ no__t-0 para obtener información sobre cómo hospedar el lienzo de diseño del diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="11d63-120">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>

## <a name="see-also"></a><span data-ttu-id="11d63-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="11d63-121">See also</span></span>

- [<span data-ttu-id="11d63-122">Rehospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="11d63-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- <span data-ttu-id="11d63-123">@no__t 0Task 2: Hospede el Diseñador de flujo de trabajo @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="11d63-123">[Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md)</span></span>
