---
title: Cómo obtener acceso a un servicio desde una aplicación de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
ms.openlocfilehash: 178fb04244cb3e5075722877fdd3e2b5a92b8502
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309321"
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a>Cómo obtener acceso a un servicio desde una aplicación de flujo de trabajo
En este tema, se describe cómo llamar a un servicio de flujo de trabajo desde una aplicación de consola de flujo de trabajo. Depende de finalización de la [Cómo: Crear un servicio de flujo de trabajo con actividades de mensajería](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) tema. Aunque en este tema describe cómo llamar a un servicio de flujo de trabajo desde una aplicación de flujo de trabajo, se pueden usar los mismos métodos para llamar a cualquier servicio de Windows Communication Foundation (WCF) desde una aplicación de flujo de trabajo.

### <a name="create-a-workflow-console-application-project"></a>Creación de un proyecto de aplicación de consola de flujo de trabajo

1. Start Visual Studio 2012.

2. Cargue el proyecto MyWFService que creó en el [Cómo: Crear un servicio de flujo de trabajo con actividades de mensajería](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) tema.

3. Haga clic en el **MyWFService** solución en el **el Explorador de soluciones** y seleccione **agregar**, **nuevo proyecto**. Seleccione **flujo de trabajo** en el **plantillas instaladas** y **aplicación de consola de flujos de trabajo** en la lista de tipos de proyecto. Denomine el MyWFClient del proyecto y use la ubicación predeterminada tal y como se muestra en la siguiente ilustración.

     ![Cuadro de diálogo Agregar nuevo proyecto](./media/how-to-access-a-service-from-a-workflow-application/add-new-project-dialog.jpg)

     Haga clic en el **Aceptar** botón para descartar el **cuadro de diálogo Agregar nuevo proyecto**.

4. Una vez creado el proyecto, el archivo Workflow1.xaml se abre en el diseñador. Haga clic en el **cuadro de herramientas** ficha para abrir el cuadro de herramientas si no está ya abierto y haga clic en la chincheta para mantener abierta la ventana de cuadro de herramientas.

5. Presione **Ctrl**+**F5** para generar e iniciar el servicio. Como antes, se inicia el servidor de desarrollo de ASP.NET e Internet Explorer muestra la página de ayuda de WCF. Observe el URI de esta página, ya que deberá usarlo en el paso siguiente.

     ![Mostrar la página de ayuda WCF y URI de IE](./media/how-to-access-a-service-from-a-workflow-application/ie-wcf-help-page-uri.jpg)

6. Haga clic en el **MyWFClient** del proyecto en el **el Explorador de soluciones** y seleccione **agregar** > **referencia de servicio**. Haga clic en el **Discover** botón para buscar la solución actual para todos los servicios. Haga clic en el triángulo situado junto a Service1.xamlx en la lista de servicios. Haga clic en el triángulo situado junto a Service1 para hacer una lista de los contratos implementados por el servicio Service1. Expanda el **Service1** nodo en el **servicios** lista. La operación de eco que se muestra en el **operaciones** lista tal como se muestra en la siguiente ilustración.

     ![Cuadro de diálogo Agregar referencia de servicio](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference.jpg)

     Mantener el espacio de nombres predeterminado y haga clic en **Aceptar** para descartar el **Add Service Reference** cuadro de diálogo. Se muestra el siguiente cuadro de diálogo.

     ![Agregar cuadro de diálogo de notificación de referencia de servicio](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference-dialog.jpg)

     Haga clic en **Aceptar** para descartar el cuadro de diálogo. Después, presione CTRL+MAYÚS+B para compilar la solución. Observe que en el cuadro de herramientas se ha agregado una nueva sección denominada **MyWFClient.ServiceReference1.Activities**. Expanda esta sección y observe la actividad de eco agregada como se muestra en la siguiente ilustración.

     ![Actividad de eco en el cuadro de herramientas](./media/how-to-access-a-service-from-a-workflow-application/echo-activity-toolbox.jpg)

7. Arrastre y coloque una actividad <xref:System.Activities.Statements.Sequence> en la superficie del diseñador. Se encuentra en la **flujo de Control** sección del cuadro de herramientas.

8. Con el <xref:System.Activities.Statements.Sequence> actividad en el foco, haga clic en el **Variables** vincular y agregue una variable de cadena denominada `inString`. Asigne a la variable un valor predeterminado de `"Hello, world"` , así como una variable de cadena denominada `outString` tal como se muestra en el diagrama siguiente.

     ![Agregar una variable inString](./media/how-to-access-a-service-from-a-workflow-application/add-instring-variable.jpg)

9. Arrastre y coloque una **Echo** actividad en el <xref:System.Activities.Statements.Sequence>. En la ventana Propiedades de enlace el `inMsg` argumento para el `inString` variable y la `outMsg` argumento para el `outString` variable tal como se muestra en la siguiente ilustración. Esto pasa el valor de la variable `inString` a la operación y, a continuación, toma el valor devuelto y lo coloca en la variable `outString`.

     ![Enlazar los argumentos a las variables](./media/how-to-access-a-service-from-a-workflow-application/bind-arguments-variables.jpg)

10. Arrastre y coloque un **WriteLine** actividad debajo el **Echo** actividad para mostrar la cadena devuelta por la llamada al servicio. El **WriteLine** actividad se encuentra en la **primitivas** nodo en el cuadro de herramientas. Enlazar el **texto** argumento de la **WriteLine** actividad a la `outString` variable escribiendo `outString` en el cuadro de texto en el **WriteLine** actividad. El flujo de trabajo debería tener el mismo aspecto que la siguiente ilustración.

     ![Flujo de trabajo del cliente completo](./media/how-to-access-a-service-from-a-workflow-application/complete-client-workflow.jpg)

11. Haga clic en la solución MyWFService y seleccione **Establecer proyectos de inicio...** . Seleccione el **varios proyectos de inicio** botón de radio y seleccione **iniciar** para cada proyecto en el **acción** columna tal como se muestra en la siguiente ilustración.

     ![Opciones de proyecto de inicio](./media/how-to-access-a-service-from-a-workflow-application/startup-project-options.jpg)

12. Presione Ctrl + F5 para iniciar el servicio y el cliente. El servidor de desarrollo de ASP.NET hospeda el servicio, Internet Explorer muestra la página de ayuda WCF y la aplicación de flujo de trabajo de cliente se inicia en una ventana de consola y muestra la cadena devuelta desde el servicio ("Hello, world").

## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Filtrar para crear un servicio de flujo de trabajo con actividades de mensajería](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)
- [Usar un servicio WCF desde un flujo de trabajo en un proyecto web](https://go.microsoft.com/fwlink/?LinkId=207725)
