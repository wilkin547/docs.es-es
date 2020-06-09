---
title: Procedimiento para crear un servicio de flujo de trabajo con actividades de mensajería
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: b4991fc9f8a6c45cae3943f1506247c42ed2b30b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597129"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a>Procedimiento para crear un servicio de flujo de trabajo con actividades de mensajería
En este tema, se describe cómo crear un servicio de flujo de trabajo simple mediante actividades de mensajería. Este tema se centra en los sistemas de creación de un servicio de flujo de trabajo compuesto solo por actividades de mensajería. En un servicio real, el flujo de trabajo contiene muchas otras actividades. El servicio implementa una operación denominada Eco, que toma una cadena y la devuelve al autor de la llamada. Este tema es el primero en una serie de dos temas. En el tema siguiente [Cómo: obtener acceso a un servicio desde una aplicación de flujo de trabajo](how-to-access-a-service-from-a-workflow-application.md) se describe cómo crear una aplicación de flujo de trabajo que pueda llamar al servicio creado en este tema.  
  
### <a name="to-create-a-workflow-service-project"></a>Para crear un proyecto de servicio de flujo de trabajo  
  
1. Inicie Visual Studio 2012.  
  
2. Haga clic en el menú **archivo** , seleccione **nuevo**y **proyecto** para mostrar el **cuadro de diálogo nuevo proyecto**. Seleccione **flujo de trabajo** en la lista de plantillas instaladas y **aplicación de servicio de flujo de trabajo WCF** en la lista de tipos de proyecto. Asigne un nombre al proyecto `MyWFService` y use la ubicación predeterminada, tal como se muestra en la siguiente ilustración.  
  
     Haga clic en el botón **Aceptar** para descartar el **cuadro de diálogo nuevo proyecto**.  
  
3. Cuando se crea el proyecto, el archivo Service1.xamlx se abre en el diseñador tal y como se muestra en la siguiente ilustración.  
  
     ![Captura de pantalla que muestra el archivo Service1. xamlx abierto en el diseñador.](./media/how-to-create-a-workflow-service-with-messaging-activities/default-workflow-service.jpg)  
  
     Haga clic con el botón derecho en la actividad denominada **servicio secuencial** y seleccione **eliminar**.  
  
### <a name="to-implement-the-workflow-service"></a>Para implementar el servicio de flujo de trabajo  
  
1. Seleccione la pestaña **cuadro de herramientas** en el lado izquierdo de la pantalla para mostrar el cuadro de herramientas y haga clic en el marcador para mantener la ventana abierta. Expanda la sección **Mensajería** del cuadro de herramientas para mostrar las actividades de mensajería y las plantillas de actividad de mensajería, tal como se muestra en la siguiente ilustración.  
  
     ![Captura de pantalla que muestra el cuadro de herramientas con la sección de mensajería expandida.](./media/how-to-create-a-workflow-service-with-messaging-activities/toolbox-messaging-section.jpg)  
  
2. Arrastre y coloque una plantilla **ReceiveAndSendReply** en el diseñador de flujo de trabajo. Esto crea una <xref:System.Activities.Statements.Sequence> actividad con una actividad **Receive** seguida de una <xref:System.ServiceModel.Activities.SendReply> actividad, tal como se muestra en la siguiente ilustración.  
  
     ![Captura de pantalla que muestra la plantilla ReceiveAndSendReply.](./media/how-to-create-a-workflow-service-with-messaging-activities/receiveandsendreply-template.jpg)  
  
     Tenga en cuenta que la propiedad <xref:System.ServiceModel.Activities.SendReply> de la actividad <xref:System.ServiceModel.Activities.SendReply.Request%2A> está establecida en `Receive`, el nombre de la actividad <xref:System.ServiceModel.Activities.Receive> a la que responde la actividad <xref:System.ServiceModel.Activities.SendReply>.  
  
3. En el <xref:System.ServiceModel.Activities.Receive> tipo de actividad, `Echo` en el cuadro de texto con la etiqueta **OperationName**. Esto define el nombre de la operación que implementa el servicio.  
  
     ![Captura de pantalla que muestra dónde especificar el nombre de la operación.](./media/how-to-create-a-workflow-service-with-messaging-activities/define-operation-name.jpg)  
  
4. Con la <xref:System.ServiceModel.Activities.Receive> actividad seleccionada, abra la ventana Propiedades si aún no está abierta; para ello, haga clic en el menú **Ver** y seleccione **ventana Propiedades**. En la **ventana Propiedades** , desplácese hacia abajo hasta que vea **CanCreateInstance** y haga clic en la casilla como se muestra en la siguiente ilustración. Esta opción permite que el host de servicio de flujo de trabajo cree una nueva instancia del servicio, si es necesario, cuando se recibe un mensaje.  
  
     ![Captura de pantalla que muestra la propiedad CanCreateInstance.](./media/how-to-create-a-workflow-service-with-messaging-activities/cancreateinstance-property.jpg)  
  
5. Seleccione la <xref:System.Activities.Statements.Sequence> actividad y haga clic en el botón **variables** en la esquina inferior izquierda del diseñador. Esto muestra el editor de variables. Haga clic en el vínculo **crear variable** para agregar una variable que almacene la cadena enviada a la operación. Asigne un nombre `msg` a la variable y establezca su tipo de **variable** en cadena, tal y como se muestra en la siguiente ilustración.  
  
     ![Captura de pantalla que muestra cómo agregar una variable.](./media/how-to-create-a-workflow-service-with-messaging-activities/add-variable-msg-string.jpg)  
  
     Vuelva a hacer clic en el botón **variables** para cerrar el editor de variables.  
  
6. Haga clic **en el.** en el cuadro de texto **contenido** de la <xref:System.ServiceModel.Activities.Receive> actividad para mostrar el cuadro de diálogo **definición de contenido** . Seleccione el botón de radio **parámetros** , haga clic en el vínculo **Agregar nuevo parámetro** , escriba `inMsg` en el cuadro de texto **nombre** , seleccione **cadena** en el cuadro de lista desplegable **tipo** y escriba `msg` en el cuadro de texto **asignar a** , tal como se muestra en la siguiente ilustración.  
  
     ![Captura de pantalla que muestra cómo agregar el contenido de los parámetros.](./media/how-to-create-a-workflow-service-with-messaging-activities/adding-parameters-content.jpg)  
  
     Esto especifica que la actividad de recepción recibe el parámetro de cadena y que los datos se enlazan a la variable `msg`. Haga clic en **Aceptar** para cerrar el cuadro de diálogo **definición de contenido** .  
  
7. Haga clic en el vínculo **definir...** en el cuadro **contenido** de la <xref:System.ServiceModel.Activities.SendReply> actividad para mostrar el cuadro de diálogo **definición de contenido** . Seleccione el botón de radio **parámetros** , haga clic en el vínculo **Agregar nuevo parámetro** , escriba `outMsg` en el cuadro de texto **nombre** , seleccione **cadena** en el cuadro de lista desplegable **tipo** y, `msg` en el cuadro de texto **valor** , tal y como se muestra en la siguiente ilustración.  
  
     ![Captura de pantalla que muestra cómo agregar el parámetro outMsg.](./media/how-to-create-a-workflow-service-with-messaging-activities/outmsg-parameters-content.jpg)  
  
     Esto especifica que la actividad <xref:System.ServiceModel.Activities.SendReply> envía un mensaje o un tipo de contrato de mensaje y esos datos están enlazados a la variable `msg`. Dado que ésta es una actividad <xref:System.ServiceModel.Activities.SendReply>, esto significa que los datos de `msg` se usan para rellenar el mensaje que la actividad devuelve al cliente. Haga clic en **Aceptar** para cerrar el cuadro de diálogo **definición de contenido** .  
  
8. Guarde y compile la solución. para ello, haga clic en el menú **compilar** y seleccione **compilar solución**.  
  
## <a name="configure-the-workflow-service-project"></a>Configuración del proyecto de servicio de flujo de trabajo  
 El servicio del flujo de trabajo ha finalizado. En esta sección, se explica cómo configurar la solución de servicio de flujo de trabajo para facilitar el hospedaje y la ejecución. Esta solución usa el servidor de desarrollo de ASP.NET para hospedar el servicio.  
  
#### <a name="to-set-project-start-up-options"></a>Para establecer opciones de inicio de proyecto  
  
1. En el **Explorador de soluciones**, haga clic con el botón secundario en **MyWFService** y seleccione **propiedades** para mostrar el cuadro de diálogo **propiedades del proyecto** .  
  
2. Seleccione la pestaña **Web** y seleccione **página específica** en **acción de inicio** y escriba `Service1.xamlx` en el cuadro de texto, tal como se muestra en la siguiente ilustración.  
  
     ![Captura de pantalla que muestra el cuadro de diálogo Propiedades del proyecto.](./media/how-to-create-a-workflow-service-with-messaging-activities/project-properties-dialog.jpg)  
  
     Esto hospeda el servicio definido en Service1.xamlx en el servidor de desarrollo de ASP.NET.  
  
3. Presione Ctrl + F5 para iniciar el servicio. El icono del servidor de desarrollo de ASP.NET se muestra en el lado inferior derecho del escritorio, tal y como se muestra en la siguiente imagen.  
  
     ![Captura de pantalla que muestra el icono del servidor de desarrolladores de ASP.NET.](./media/how-to-create-a-workflow-service-with-messaging-activities/asp-net-dev-server-icon.jpg)  
  
     Además, Internet Explorer muestra la página de ayuda del servicio WCF para el servicio.  
  
     ![Captura de pantalla que muestra la página de ayuda del servicio WCF.](./media/how-to-create-a-workflow-service-with-messaging-activities/wcf-service-help-page.jpg)  
  
4. Continúe con el tema [Cómo: obtener acceso a un servicio desde una aplicación de flujo de trabajo](how-to-access-a-service-from-a-workflow-application.md) para crear un cliente de flujo de trabajo que llame a este servicio.  
  
## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](workflow-services.md)
- [Hospedar información general de servicios de flujo de trabajo](hosting-workflow-services-overview.md)
- [Actividades de mensajería](messaging-activities.md)
