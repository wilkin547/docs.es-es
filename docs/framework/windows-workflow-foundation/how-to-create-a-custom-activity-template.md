---
title: Procedimiento para crear una plantilla de actividad personalizada
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: 90a54806833ff66797fb7beaa6ac8a912665bddc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280122"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="a4abc-102">Procedimiento para crear una plantilla de actividad personalizada</span><span class="sxs-lookup"><span data-stu-id="a4abc-102">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="a4abc-103">Las plantillas de actividad personalizadas se utilizan para personalizar la configuración de actividades, incluidas las actividades compuestas personalizadas, para que los usuarios no tengan que crear cada actividad de forma individual y configurar propiedades y otros valores manualmente.</span><span class="sxs-lookup"><span data-stu-id="a4abc-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="a4abc-104">Estas plantillas personalizadas pueden estar disponibles en el **cuadro de herramientas** en el diseñador de flujo de trabajo de Windows o en un diseñador hospedado en otro host, desde el que los usuarios pueden arrastrarlas a la superficie de diseño preconfigurada.</span><span class="sxs-lookup"><span data-stu-id="a4abc-104">These custom templates can be made available in the **Toolbox** on the Windows Workflow Designer or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> <span data-ttu-id="a4abc-105">Diseñador de flujo de trabajo incluye buenos ejemplos de estas plantillas: el [Diseñador de plantillas SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) y el [Diseñador de plantillas ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) en la categoría [diseñadores de actividad de mensajería](/visualstudio/workflow-designer/messaging-activity-designers) .</span><span class="sxs-lookup"><span data-stu-id="a4abc-105">Workflow Designer ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="a4abc-106">En el primer procedimiento de este tema se describe cómo crear una plantilla de actividad personalizada para una actividad de **retraso** y el segundo procedimiento describe brevemente cómo hacer que esté disponible en un diseñador de flujo de trabajo para comprobar que la plantilla personalizada funciona.</span><span class="sxs-lookup"><span data-stu-id="a4abc-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a Workflow Designer to verify that the custom template works.</span></span>

 <span data-ttu-id="a4abc-107">Las plantillas de actividad personalizadas deben implementar la <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span><span class="sxs-lookup"><span data-stu-id="a4abc-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="a4abc-108">La interfaz tiene un método <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> único con el que puede crear y configurar las instancias de actividad utilizadas en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a4abc-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="a4abc-109">Para crear una plantilla para la actividad Delay</span><span class="sxs-lookup"><span data-stu-id="a4abc-109">To create a template for the Delay activity</span></span>

1. <span data-ttu-id="a4abc-110">Inicie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="a4abc-110">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="a4abc-111">En el menú **Archivo** , seleccione **Nuevo** y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a4abc-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="a4abc-112">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="a4abc-112">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="a4abc-113">En el panel **tipos de proyecto** , seleccione flujo de **trabajo** de los proyectos de **Visual C#** o agrupaciones de **Visual Basic** en función de su preferencia de idioma.</span><span class="sxs-lookup"><span data-stu-id="a4abc-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4. <span data-ttu-id="a4abc-114">En el panel **plantillas** , seleccione **biblioteca de actividades**.</span><span class="sxs-lookup"><span data-stu-id="a4abc-114">In the **Templates** pane, select **Activity Library**.</span></span>

5. <span data-ttu-id="a4abc-115">En el cuadro **Nombre**, escriba `DelayActivityTemplate`.</span><span class="sxs-lookup"><span data-stu-id="a4abc-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6. <span data-ttu-id="a4abc-116">Acepte los valores predeterminados en los cuadros de texto **Ubicación** y nombre de la **solución** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4abc-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7. <span data-ttu-id="a4abc-117">Haga clic con el botón secundario en el directorio referencias del proyecto DelayActivityTemplate en **Explorador de soluciones** y elija **Agregar referencia** para abrir el cuadro de diálogo **Agregar referencia** .</span><span class="sxs-lookup"><span data-stu-id="a4abc-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8. <span data-ttu-id="a4abc-118">Vaya a la pestaña **.net** y seleccione **PresentationFramework** en la columna **nombre de componente** de la izquierda y haga clic en **aceptar** para agregar una referencia al archivo PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="a4abc-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="a4abc-119">Repita este procedimiento para agregar referencias a los archivos System.Activities.Presentation.dll y WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="a4abc-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="a4abc-120">Haga clic con el botón derecho en el proyecto DelayActivityTemplate en **Explorador de soluciones** y elija **Agregar** y, a continuación, **nuevo elemento** para abrir el cuadro de diálogo **Agregar nuevo elemento** .</span><span class="sxs-lookup"><span data-stu-id="a4abc-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="a4abc-121">Seleccione la plantilla **clase** , asígnele el nombre MyDelayTemplate y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4abc-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="a4abc-122">Abra el archivo MyDelayTemplate.cs y agregue las siguientes instrucciones.</span><span class="sxs-lookup"><span data-stu-id="a4abc-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```csharp
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="a4abc-123">Implemente la interfaz <xref:System.Activities.Presentation.IActivityTemplateFactory> con la clase `MyDelayActivity` mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4abc-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="a4abc-124">De esta manera configura el retraso para una duración de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="a4abc-124">This configures the delay to have a duration of 10 seconds.</span></span>

    ```csharp
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

14. <span data-ttu-id="a4abc-125">Seleccione **compilar solución** en el menú **compilar** para generar el archivo de DelayActivityTemplate.dll.</span><span class="sxs-lookup"><span data-stu-id="a4abc-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="a4abc-126">Para que la plantilla esté disponible en un Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a4abc-126">To make the template available in a Workflow Designer</span></span>

1. <span data-ttu-id="a4abc-127">Haga clic con el botón secundario en la solución DelayActivityTemplate en **Explorador de soluciones** y elija **Agregar** y, a continuación, **nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="a4abc-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="a4abc-128">Seleccione la plantilla **aplicación de consola de flujos de trabajo** , asígnele el nombre `CustomActivityTemplateApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4abc-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3. <span data-ttu-id="a4abc-129">Haga clic con el botón secundario en el directorio referencias del proyecto CustomActivityTemplateApp en **Explorador de soluciones** y elija **Agregar referencia** para abrir el cuadro de diálogo **Agregar referencia** .</span><span class="sxs-lookup"><span data-stu-id="a4abc-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4. <span data-ttu-id="a4abc-130">Vaya a la pestaña **proyectos** y seleccione **DelayActivityTemplate** en la columna **nombre del proyecto** de la izquierda y haga clic en **aceptar** para agregar una referencia al archivo DelayActivityTemplate.dll que creó en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a4abc-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5. <span data-ttu-id="a4abc-131">Haga clic con el botón derecho en el proyecto CustomActivityTemplateApp en **Explorador de soluciones** **y elija compilar** para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4abc-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6. <span data-ttu-id="a4abc-132">Haga clic con el botón derecho en el proyecto CustomActivityTemplateApp en **Explorador de soluciones** y elija **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="a4abc-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7. <span data-ttu-id="a4abc-133">Seleccione **iniciar sin depurar** en el menú **depurar** y presione cualquier tecla para continuar cuando se le solicite desde la ventana de cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="a4abc-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8. <span data-ttu-id="a4abc-134">Abra el archivo Workflow1. XAML y abra el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="a4abc-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="a4abc-135">Busque la plantilla **MyDelayActivity** en la categoría **DelayActivityTemplate** .</span><span class="sxs-lookup"><span data-stu-id="a4abc-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="a4abc-136">Arrástrela a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="a4abc-136">Drag it onto the design surface.</span></span> <span data-ttu-id="a4abc-137">En la ventana **propiedades** , compruebe que la propiedad se ha `Duration` establecido en 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="a4abc-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="a4abc-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4abc-138">Example</span></span>

 <span data-ttu-id="a4abc-139">El archivo MyDelayActivity.cs debería contener el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="a4abc-139">The MyDelayActivity.cs file should contain the following code.</span></span>

```csharp
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

## <a name="see-also"></a><span data-ttu-id="a4abc-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4abc-140">See also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="a4abc-141">Personalizar la experiencia de diseño del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a4abc-141">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
