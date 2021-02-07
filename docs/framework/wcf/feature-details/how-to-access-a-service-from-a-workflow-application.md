---
description: 'Más información acerca de cómo: obtener acceso a un servicio desde una aplicación de flujo de trabajo'
title: Cómo obtener acceso a un servicio desde una aplicación de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
ms.openlocfilehash: f8972bf7755c0103d164633d53d8d32508ce2efe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743101"
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a>Cómo obtener acceso a un servicio desde una aplicación de flujo de trabajo

En este tema, se describe cómo llamar a un servicio de flujo de trabajo desde una aplicación de consola de flujo de trabajo. Depende de la finalización del tema [Cómo: crear un servicio de flujo de trabajo con actividades de mensajería](how-to-create-a-workflow-service-with-messaging-activities.md) . Aunque en este tema se describe cómo llamar a un servicio de flujo de trabajo desde una aplicación de flujo de trabajo, se pueden usar los mismos métodos para llamar a cualquier servicio Windows Communication Foundation (WCF) desde una aplicación de flujo de trabajo.

### <a name="create-a-workflow-console-application-project"></a>Creación de un proyecto de aplicación de consola de flujo de trabajo

1. Inicie Visual Studio 2012.

2. Cargue el proyecto MyWFService que creó en el tema [Cómo: crear un servicio de flujo de trabajo con actividades de mensajería](how-to-create-a-workflow-service-with-messaging-activities.md) .

3. Haga clic con el botón derecho en la solución **MyWFService** en el **Explorador de soluciones** y seleccione **Agregar**, **nuevo proyecto**. Seleccione **flujo de trabajo** en las **plantillas instaladas** y la **aplicación de consola de flujos de trabajo** en la lista de tipos de proyecto. Denomine el MyWFClient del proyecto y use la ubicación predeterminada tal y como se muestra en la siguiente ilustración.

     ![Cuadro de diálogo Agregar nuevo proyecto](./media/how-to-access-a-service-from-a-workflow-application/add-new-project-dialog.jpg)

     Haga clic en el botón **Aceptar** para descartar el **cuadro de diálogo Agregar nuevo proyecto**.

4. Una vez creado el proyecto, el archivo Workflow1.xaml se abre en el diseñador. Haga clic en la pestaña **cuadro de herramientas** para abrir el cuadro de herramientas, si aún no está abierto, y haga clic en el marcador para mantener abierta la ventana del cuadro de herramientas.

5. Presione **Ctrl** + **F5** para compilar e iniciar el servicio. Como antes, se inicia el servidor de desarrollo de ASP.NET e Internet Explorer muestra la página de ayuda de WCF. Observe el URI de esta página, ya que deberá usarlo en el paso siguiente.

     ![IE que muestra la página de ayuda de WCF y el URI](./media/how-to-access-a-service-from-a-workflow-application/ie-wcf-help-page-uri.jpg)

6. Haga clic con el botón derecho en el proyecto **MyWFClient** en el **Explorador de soluciones** y seleccione **Agregar**  >  **referencia de servicio**. Haga clic en el botón **detectar** para buscar todos los servicios en la solución actual. Haga clic en el triángulo situado junto a Service1.xamlx en la lista de servicios. Haga clic en el triángulo situado junto a Service1 para hacer una lista de los contratos implementados por el servicio Service1. Expanda el nodo **Service1** en la lista de **servicios** . La operación de eco se muestra en la lista de **operaciones** , tal y como se muestra en la siguiente ilustración.

     ![Cuadro de diálogo Agregar referencia de servicio](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference.jpg)

     Mantenga el espacio de nombres predeterminado y haga clic en **Aceptar** para descartar el cuadro de diálogo **Agregar referencia de servicio** . Se muestra el siguiente cuadro de diálogo.

     ![Cuadro de diálogo de notificación de Agregar referencia de servicio](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference-dialog.jpg)

     Haga clic en **Aceptar** para descartar el cuadro de diálogo. Después, presione CTRL+MAYÚS+B para compilar la solución. Observe en el cuadro de herramientas se ha agregado una nueva sección llamada **MyWFClient. ServiceReference1. Activities**. Expanda esta sección y observe la actividad de eco agregada como se muestra en la siguiente ilustración.

     ![Actividad de eco en el cuadro de herramientas](./media/how-to-access-a-service-from-a-workflow-application/echo-activity-toolbox.jpg)

7. Arrastre y coloque una actividad <xref:System.Activities.Statements.Sequence> en la superficie del diseñador. Está en la sección **flujo de control** del cuadro de herramientas.

8. Con la <xref:System.Activities.Statements.Sequence> actividad en el foco, haga clic en el vínculo **variables** y agregue una variable de cadena denominada `inString` . Asigne a la variable un valor predeterminado de `"Hello, world"` , así como una variable de cadena denominada `outString` como se muestra en el diagrama siguiente.

     ![Agregar una variable instring](./media/how-to-access-a-service-from-a-workflow-application/add-instring-variable.jpg)

9. Arrastre y coloque una actividad de **eco** en el <xref:System.Activities.Statements.Sequence> . En la ventana Propiedades, enlace el `inMsg` argumento a la `inString` variable y el `outMsg` argumento a la `outString` variable tal y como se muestra en la siguiente ilustración. Esto pasa el valor de la variable `inString` a la operación y, a continuación, toma el valor devuelto y lo coloca en la variable `outString`.

     ![Enlazar los argumentos a las variables](./media/how-to-access-a-service-from-a-workflow-application/bind-arguments-variables.jpg)

10. Arrastre y coloque una actividad **WriteLine** debajo de la actividad **echo** para mostrar la cadena devuelta por la llamada de servicio. La actividad **WriteLine** se encuentra en el nodo **primitivas** del cuadro de herramientas. Enlace el argumento de **texto** de la actividad **WriteLine** a la `outString` variable escribiendo `outString` en el cuadro de texto de la actividad **WriteLine** . El flujo de trabajo debería tener el mismo aspecto que la siguiente ilustración.

     ![Flujo de trabajo del cliente completo](./media/how-to-access-a-service-from-a-workflow-application/complete-client-workflow.jpg)

11. Haga clic con el botón derecho en la solución MyWFService y seleccione **establecer proyectos de inicio..**.. Seleccione el botón de radio **proyectos de inicio múltiples** y seleccione **iniciar** para cada proyecto en la columna **acción** , tal como se muestra en la siguiente ilustración.

     ![Opciones de proyecto de inicio](./media/how-to-access-a-service-from-a-workflow-application/startup-project-options.jpg)

12. Presione Ctrl + F5 para iniciar el servicio y el cliente. El Servidor de desarrollo de ASP.NET hospeda el servicio, Internet Explorer muestra la página de ayuda de WCF y la aplicación de flujo de trabajo de cliente se inicia en una ventana de consola y muestra la cadena devuelta por el servicio ("Hello, World").

## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](workflow-services.md)
- [Procedimiento para crear un servicio de flujo de trabajo con actividades de mensajería](how-to-create-a-workflow-service-with-messaging-activities.md)
- [Usar un servicio WCF desde un flujo de trabajo en un proyecto web](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
