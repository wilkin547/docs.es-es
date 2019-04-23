---
title: Procedimiento para crear una plantilla de actividad personalizada
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: ee6f249092c5cf8643e3c9bfd15d32e77791d8bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295853"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="25d71-102">Procedimiento para crear una plantilla de actividad personalizada</span><span class="sxs-lookup"><span data-stu-id="25d71-102">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="25d71-103">Las plantillas de actividad personalizadas se utilizan para personalizar la configuración de actividades, incluidas las actividades compuestas personalizadas, para que los usuarios no tengan que crear cada actividad de forma individual y configurar propiedades y otros valores manualmente.</span><span class="sxs-lookup"><span data-stu-id="25d71-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="25d71-104">Estas plantillas personalizadas pueden estar disponibles en el **cuadro de herramientas** en el [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] o desde un diseñador rehospedado, desde el que los usuarios pueden arrastrarlas a la superficie de diseño preconfigurada.</span><span class="sxs-lookup"><span data-stu-id="25d71-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] <span data-ttu-id="25d71-105">se suministra con buenos ejemplos de esas plantillas: el [Diseñador de plantillas SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) y [Diseñador de plantillas ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) en el [diseñadores de actividades de mensajería](/visualstudio/workflow-designer/messaging-activity-designers) categoría.</span><span class="sxs-lookup"><span data-stu-id="25d71-105">ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="25d71-106">El primer procedimiento de este tema describe cómo crear una plantilla de actividad personalizada para un **retraso** actividad y el segundo procedimiento describe brevemente cómo que esté disponible en un [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] para comprobar que funciona la plantilla personalizada.</span><span class="sxs-lookup"><span data-stu-id="25d71-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>

 <span data-ttu-id="25d71-107">Las plantillas de actividad personalizadas deben implementar la <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span><span class="sxs-lookup"><span data-stu-id="25d71-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="25d71-108">La interfaz tiene un método <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> único con el que puede crear y configurar las instancias de actividad utilizadas en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="25d71-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="25d71-109">Para crear una plantilla para la actividad Delay</span><span class="sxs-lookup"><span data-stu-id="25d71-109">To create a template for the Delay activity</span></span>

1. <span data-ttu-id="25d71-110">Inicie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="25d71-110">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="25d71-111">En el menú **Archivo**, elija **Nuevo** y después seleccione **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="25d71-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="25d71-112">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="25d71-112">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="25d71-113">En el **tipos de proyecto** panel, seleccione **flujo de trabajo** desde el **Visual C#** proyectos o **Visual Basic** agrupaciones en función de su preferencia de idioma.</span><span class="sxs-lookup"><span data-stu-id="25d71-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4. <span data-ttu-id="25d71-114">En el **plantillas** panel, seleccione **biblioteca de actividades**.</span><span class="sxs-lookup"><span data-stu-id="25d71-114">In the **Templates** pane, select **Activity Library**.</span></span>

5. <span data-ttu-id="25d71-115">En el **nombre** , escriba `DelayActivityTemplate`.</span><span class="sxs-lookup"><span data-stu-id="25d71-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6. <span data-ttu-id="25d71-116">Acepte los valores predeterminados en el **ubicación** y **nombre de la solución** cuadros de texto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25d71-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7. <span data-ttu-id="25d71-117">Haga clic en el directorio referencias del proyecto DelayActivityTemplate en **el Explorador de soluciones** y elija **Agregar referencia** para abrir el **Agregar referencia** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="25d71-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8. <span data-ttu-id="25d71-118">Vaya a la **.NET** pestaña y seleccione **PresentationFramework** desde el **nombre del componente** columna a la izquierda y haga clic en **Aceptar** para agregar una referencia en el archivo PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="25d71-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="25d71-119">Repita este procedimiento para agregar referencias a los archivos System.Activities.Presentation.dll y WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="25d71-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="25d71-120">Haga clic en el proyecto DelayActivityTemplate en **el Explorador de soluciones** y elija **agregar** y, a continuación, **nuevo elemento** para abrir el **Agregar nuevo elemento**cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="25d71-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="25d71-121">Seleccione el **clase** plantilla, denomínela MyDelayTemplate y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25d71-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="25d71-122">Abra el archivo MyDelayTemplate.cs y agregue las siguientes instrucciones.</span><span class="sxs-lookup"><span data-stu-id="25d71-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="25d71-123">Implemente la interfaz <xref:System.Activities.Presentation.IActivityTemplateFactory> con la clase `MyDelayActivity` mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="25d71-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="25d71-124">De esta manera configura el retraso para una duración de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="25d71-124">This configures the delay to have a duration of 10 seconds.</span></span>

    ```
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
    ```

14. <span data-ttu-id="25d71-125">Seleccione **compilar solución** desde el **compilar** menú para generar el archivo DelayActivityTemplate.dll.</span><span class="sxs-lookup"><span data-stu-id="25d71-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="25d71-126">Para que la plantilla esté disponible en un Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="25d71-126">To make the template available in a Workflow Designer</span></span>

1. <span data-ttu-id="25d71-127">Haga clic en la solución DelayActivityTemplate en **el Explorador de soluciones** y elija **agregar** y, a continuación, **nuevo proyecto** para abrir el **Agregar nuevo proyecto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="25d71-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="25d71-128">Seleccione el **aplicación de consola de flujos de trabajo** plantilla, asígnele el nombre `CustomActivityTemplateApp`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25d71-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3. <span data-ttu-id="25d71-129">Haga clic en el directorio referencias del proyecto CustomActivityTemplateApp en **el Explorador de soluciones** y elija **Agregar referencia** para abrir el **Agregar referencia** cuadro de diálogo cuadro.</span><span class="sxs-lookup"><span data-stu-id="25d71-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4. <span data-ttu-id="25d71-130">Vaya a la **proyectos** pestaña y seleccione **DelayActivityTemplate** desde el **nombre del proyecto** columna a la izquierda y haga clic en **Aceptar** para agregar un hacer referencia al archivo DelayActivityTemplate.dll que creó en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="25d71-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5. <span data-ttu-id="25d71-131">Haga clic en el proyecto CustomActivityTemplateApp en **el Explorador de soluciones** y elija **compilación** para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="25d71-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6. <span data-ttu-id="25d71-132">Haga clic en el proyecto CustomActivityTemplateApp en **el Explorador de soluciones** y elija **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="25d71-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7. <span data-ttu-id="25d71-133">Seleccione **iniciar sin depurar** desde el **depurar** menú y presione cualquier tecla para continuar cuando se le pida en la ventana de cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="25d71-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8. <span data-ttu-id="25d71-134">Abra el archivo Workflow1.xaml y abra el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="25d71-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="25d71-135">Busque el **MyDelayActivity** plantilla en el **DelayActivityTemplate** categoría.</span><span class="sxs-lookup"><span data-stu-id="25d71-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="25d71-136">Arrástrela a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="25d71-136">Drag it onto the design surface.</span></span> <span data-ttu-id="25d71-137">Confirmar en el **propiedades** ventana que el `Duration` propiedad se estableció en 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="25d71-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="25d71-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25d71-138">Example</span></span>
 <span data-ttu-id="25d71-139">El archivo MyDelayActivity.cs debería contener el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="25d71-139">The MyDelayActivity.cs file should contain the following code.</span></span>

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

//Namespaces added
using System.Activities;
using System.Activities.Statements;
using System.Activities.Presentation;
using System.Windows;

namespace DelayActivityTemplate
{
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="25d71-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="25d71-140">See also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="25d71-141">Personalización de la experiencia de diseño del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="25d71-141">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)