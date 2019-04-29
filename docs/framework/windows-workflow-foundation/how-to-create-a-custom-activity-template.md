---
title: Procedimiento para crear una plantilla de actividad personalizada
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: ee6f249092c5cf8643e3c9bfd15d32e77791d8bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773625"
---
# <a name="how-to-create-a-custom-activity-template"></a>Procedimiento para crear una plantilla de actividad personalizada

Las plantillas de actividad personalizadas se utilizan para personalizar la configuración de actividades, incluidas las actividades compuestas personalizadas, para que los usuarios no tengan que crear cada actividad de forma individual y configurar propiedades y otros valores manualmente. Estas plantillas personalizadas pueden estar disponibles en el **cuadro de herramientas** en el [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] o desde un diseñador rehospedado, desde el que los usuarios pueden arrastrarlas a la superficie de diseño preconfigurada. [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] se suministra con buenos ejemplos de esas plantillas: el [Diseñador de plantillas SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) y [Diseñador de plantillas ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) en el [diseñadores de actividades de mensajería](/visualstudio/workflow-designer/messaging-activity-designers) categoría.

 El primer procedimiento de este tema describe cómo crear una plantilla de actividad personalizada para un **retraso** actividad y el segundo procedimiento describe brevemente cómo que esté disponible en un [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] para comprobar que funciona la plantilla personalizada.

 Las plantillas de actividad personalizadas deben implementar la <xref:System.Activities.Presentation.IActivityTemplateFactory>. La interfaz tiene un método <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> único con el que puede crear y configurar las instancias de actividad utilizadas en la plantilla.

## <a name="to-create-a-template-for-the-delay-activity"></a>Para crear una plantilla para la actividad Delay

1. Inicie Visual Studio 2010.

2. En el menú **Archivo**, elija **Nuevo** y después seleccione **Proyecto**.

     Aparece el cuadro de diálogo **Nuevo proyecto** .

3. En el **tipos de proyecto** panel, seleccione **flujo de trabajo** desde el **Visual C#** proyectos o **Visual Basic** agrupaciones en función de su preferencia de idioma.

4. En el **plantillas** panel, seleccione **biblioteca de actividades**.

5. En el **nombre** , escriba `DelayActivityTemplate`.

6. Acepte los valores predeterminados en el **ubicación** y **nombre de la solución** cuadros de texto y, a continuación, haga clic en **Aceptar**.

7. Haga clic en el directorio referencias del proyecto DelayActivityTemplate en **el Explorador de soluciones** y elija **Agregar referencia** para abrir el **Agregar referencia** cuadro de diálogo.

8. Vaya a la **.NET** pestaña y seleccione **PresentationFramework** desde el **nombre del componente** columna a la izquierda y haga clic en **Aceptar** para agregar una referencia en el archivo PresentationFramework.dll.

9. Repita este procedimiento para agregar referencias a los archivos System.Activities.Presentation.dll y WindowsBase.dll.

10. Haga clic en el proyecto DelayActivityTemplate en **el Explorador de soluciones** y elija **agregar** y, a continuación, **nuevo elemento** para abrir el **Agregar nuevo elemento**cuadro de diálogo.

11. Seleccione el **clase** plantilla, denomínela MyDelayTemplate y, a continuación, haga clic en **Aceptar**.

12. Abra el archivo MyDelayTemplate.cs y agregue las siguientes instrucciones.

    ```
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. Implemente la interfaz <xref:System.Activities.Presentation.IActivityTemplateFactory> con la clase `MyDelayActivity` mediante el código siguiente. De esta manera configura el retraso para una duración de 10 segundos.

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

14. Seleccione **compilar solución** desde el **compilar** menú para generar el archivo DelayActivityTemplate.dll.

### <a name="to-make-the-template-available-in-a-workflow-designer"></a>Para que la plantilla esté disponible en un Diseñador de flujo de trabajo

1. Haga clic en la solución DelayActivityTemplate en **el Explorador de soluciones** y elija **agregar** y, a continuación, **nuevo proyecto** para abrir el **Agregar nuevo proyecto** cuadro de diálogo.

2. Seleccione el **aplicación de consola de flujos de trabajo** plantilla, asígnele el nombre `CustomActivityTemplateApp`y, a continuación, haga clic en **Aceptar**.

3. Haga clic en el directorio referencias del proyecto CustomActivityTemplateApp en **el Explorador de soluciones** y elija **Agregar referencia** para abrir el **Agregar referencia** cuadro de diálogo cuadro.

4. Vaya a la **proyectos** pestaña y seleccione **DelayActivityTemplate** desde el **nombre del proyecto** columna a la izquierda y haga clic en **Aceptar** para agregar un hacer referencia al archivo DelayActivityTemplate.dll que creó en el primer procedimiento.

5. Haga clic en el proyecto CustomActivityTemplateApp en **el Explorador de soluciones** y elija **compilación** para compilar la aplicación.

6. Haga clic en el proyecto CustomActivityTemplateApp en **el Explorador de soluciones** y elija **establecer como proyecto de inicio**.

7. Seleccione **iniciar sin depurar** desde el **depurar** menú y presione cualquier tecla para continuar cuando se le pida en la ventana de cmd.exe.

8. Abra el archivo Workflow1.xaml y abra el **cuadro de herramientas**.

9. Busque el **MyDelayActivity** plantilla en el **DelayActivityTemplate** categoría. Arrástrela a la superficie de diseño. Confirmar en el **propiedades** ventana que el `Duration` propiedad se estableció en 10 segundos.

## <a name="example"></a>Ejemplo
 El archivo MyDelayActivity.cs debería contener el siguiente código.

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

## <a name="see-also"></a>Vea también

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [Personalización de la experiencia de diseño del flujo de trabajo](customizing-the-workflow-design-experience.md)