---
title: 'Cómo: Crear una plantilla de actividad personalizada'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: f910d1367c941dbc319421d402cae8f4194872e5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715251"
---
# <a name="how-to-create-a-custom-activity-template"></a>Cómo: Crear una plantilla de actividad personalizada

Las plantillas de actividad personalizadas se utilizan para personalizar la configuración de actividades, incluidas las actividades compuestas personalizadas, para que los usuarios no tengan que crear cada actividad de forma individual y configurar propiedades y otros valores manualmente. Estas plantillas personalizadas pueden estar disponibles en el **cuadro de herramientas** en el diseñador de flujo de trabajo de Windows o en un diseñador hospedado en otro host, desde el que los usuarios pueden arrastrarlas a la superficie de diseño preconfigurada. Diseñador de flujo de trabajo incluye buenos ejemplos de estas plantillas: el [Diseñador de plantillas SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) y el [Diseñador de plantillas ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) en la categoría [diseñadores de actividad de mensajería](/visualstudio/workflow-designer/messaging-activity-designers) .

 En el primer procedimiento de este tema se describe cómo crear una plantilla de actividad personalizada para una actividad de **retraso** y el segundo procedimiento describe brevemente cómo hacer que esté disponible en un diseñador de flujo de trabajo para comprobar que la plantilla personalizada funciona.

 Las plantillas de actividad personalizadas deben implementar la <xref:System.Activities.Presentation.IActivityTemplateFactory>. La interfaz tiene un método <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> único con el que puede crear y configurar las instancias de actividad utilizadas en la plantilla.

## <a name="to-create-a-template-for-the-delay-activity"></a>Para crear una plantilla para la actividad Delay

1. Inicie Visual Studio 2010.

2. En el menú **Archivo**, elija **Nuevo** y después seleccione **Proyecto**.

     Aparece el cuadro de diálogo **Nuevo proyecto** .

3. En el panel **tipos de proyecto** , seleccione flujo de **trabajo** en los proyectos **visuales C#**  o en las agrupaciones de **Visual Basic** en función de su preferencia de idioma.

4. En el panel **plantillas** , seleccione **biblioteca de actividades**.

5. En el cuadro **nombre** , escriba `DelayActivityTemplate`.

6. Acepte los valores predeterminados en los cuadros de texto **Ubicación** y nombre de la **solución** y, a continuación, haga clic en **Aceptar**.

7. Haga clic con el botón secundario en el directorio referencias del proyecto DelayActivityTemplate en **Explorador de soluciones** y elija **Agregar referencia** para abrir el cuadro de diálogo **Agregar referencia** .

8. Vaya a la pestaña **.net** y seleccione **PresentationFramework** en la columna **nombre de componente** de la izquierda y haga clic en **Aceptar** para agregar una referencia al archivo PresentationFramework. dll.

9. Repita este procedimiento para agregar referencias a los archivos System.Activities.Presentation.dll y WindowsBase.dll.

10. Haga clic con el botón derecho en el proyecto DelayActivityTemplate en **Explorador de soluciones** y elija **Agregar** y, a continuación, **nuevo elemento** para abrir el cuadro de diálogo **Agregar nuevo elemento** .

11. Seleccione la plantilla **clase** , asígnele el nombre MyDelayTemplate y, a continuación, haga clic en **Aceptar**.

12. Abra el archivo MyDelayTemplate.cs y agregue las siguientes instrucciones.

    ```csharp
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. Implemente la interfaz <xref:System.Activities.Presentation.IActivityTemplateFactory> con la clase `MyDelayActivity` mediante el código siguiente. De esta manera configura el retraso para una duración de 10 segundos.

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

14. Seleccione **compilar solución** en el menú **compilar** para generar el archivo DelayActivityTemplate. dll.

### <a name="to-make-the-template-available-in-a-workflow-designer"></a>Para que la plantilla esté disponible en un Diseñador de flujo de trabajo

1. Haga clic con el botón secundario en la solución DelayActivityTemplate en **Explorador de soluciones** y elija **Agregar** y, a continuación, **nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto** .

2. Seleccione la plantilla **aplicación de consola de flujos de trabajo** , asígnele el nombre `CustomActivityTemplateApp`y, a continuación, haga clic en **Aceptar**.

3. Haga clic con el botón secundario en el directorio referencias del proyecto CustomActivityTemplateApp en **Explorador de soluciones** y elija **Agregar referencia** para abrir el cuadro de diálogo **Agregar referencia** .

4. Vaya a la pestaña **proyectos** y seleccione **DelayActivityTemplate** en la columna **nombre del proyecto** de la izquierda y haga clic en **Aceptar** para agregar una referencia al archivo DelayActivityTemplate. dll que creó en el primer procedimiento.

5. Haga clic con el botón derecho en el proyecto CustomActivityTemplateApp en **Explorador de soluciones** **y elija compilar** para compilar la aplicación.

6. Haga clic con el botón derecho en el proyecto CustomActivityTemplateApp en **Explorador de soluciones** y elija **establecer como proyecto de inicio**.

7. Seleccione **iniciar sin depurar** en el menú **depurar** y presione cualquier tecla para continuar cuando se le solicite desde la ventana cmd. exe.

8. Abra el archivo Workflow1. XAML y abra el **cuadro de herramientas**.

9. Busque la plantilla **MyDelayActivity** en la categoría **DelayActivityTemplate** . Arrástrela a la superficie de diseño. En la ventana **propiedades** , compruebe que la propiedad `Duration` se ha establecido en 10 segundos.

## <a name="example"></a>Ejemplo
 El archivo MyDelayActivity.cs debería contener el siguiente código.

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

## <a name="see-also"></a>Vea también

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [Personalización de la experiencia de diseño del flujo de trabajo](customizing-the-workflow-design-experience.md)
