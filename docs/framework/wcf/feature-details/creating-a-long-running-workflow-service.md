---
title: Crear un servicio de flujo de trabajo de larga ejecución
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 3e422c138b49fa19aa29e4fa1488d61a2c9bc2f8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348102"
---
# <a name="create-a-long-running-workflow-service"></a>Creación de un servicio de flujo de trabajo de ejecución prolongada

En este tema se describe cómo crear un servicio de flujo de trabajo de larga ejecución. Los servicios de flujo de trabajo de larga ejecución se pueden ejecutar durante períodos de tiempo prolongados. En algún momento, el flujo de trabajo se puede inactivar a la espera de recibir información adicional. En este caso, el flujo de trabajo se conserva en una base de datos SQL y se quita de la memoria. Cuando esté disponible la información adicional, la instancia de flujo de trabajo se vuelve a cargar en la memoria y continua ejecutándose.  En este escenario, el usuario implementa un sistema de pedidos muy simplificado.  El cliente envía un mensaje inicial al servicio de flujo de trabajo para que inicie el pedido. Devuelve un identificador de pedido al cliente. En este momento el servicio de flujo de trabajo espera otro mensaje del cliente y pasa al estado inactivo, y se conserva en una base de datos SQL Server.  Cuando el cliente envía el siguiente mensaje para pedir un elemento, el servicio de flujo de trabajo se vuelve a cargar en memoria y finaliza el procesamiento del pedido. En el ejemplo de código devuelve una cadena que indica que el elemento se ha agregado al pedido. No se pretende que el ejemplo de código sea una aplicación real de la tecnología, sino más bien un ejemplo sencillo que ilustre servicios de flujo de trabajo de ejecución prolongada. En este tema se da por hecho que sabe cómo crear proyectos y soluciones de Visual Studio 2012.

## <a name="prerequisites"></a>Requisitos previos

Debe tener instalado el siguiente software para usar este tutorial:

1. Microsoft SQL Server 2008

2. Visual Studio 2012

3. Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]

4. Está familiarizado con WCF y Visual Studio 2012 y sabe cómo crear proyectos o soluciones.

## <a name="set-up-the-sql-database"></a>Configurar el SQL Database

1. Para conservar las instancias del servicio de flujo de trabajo debe tener instalado Microsoft SQL Server y configurar una base de datos con el fin de almacenar las instancias de flujo de trabajo persistentes. Para ejecutar Microsoft SQL Management Studio, haga clic en el botón **Inicio** , seleccione **todos los programas**, **Microsoft SQL Server 2008**y **Microsoft SQL Management Studio**.

2. Haga clic en el botón **conectar** para iniciar sesión en la instancia de SQL Server

3. Haga clic con el botón derecho en **bases** de datos en la vista de árbol y seleccione **nueva base de datos.** para crear una nueva base de datos denominada `SQLPersistenceStore`.

4. Ejecute el archivo de script SqlWorkflowInstanceStoreSchema.sql ubicado en el directorio C:\Windows\Microsoft.NET\Framework\v4.0\SQL\es en la base de datos SQLPersistenceStore para configurar los esquemas de base de datos necesarios.

5. Ejecute el archivo de script SqlWorkflowInstanceStoreLogic.sql ubicado en el directorio C:\Windows\Microsoft.NET\Framework\v4.0\SQL\es en la base de datos SQLPersistenceStore para configurar la lógica de base de datos necesaria.

## <a name="create-the-web-hosted-workflow-service"></a>Crear el servicio de flujo de trabajo hospedado en Web

1. Cree una solución vacía de Visual Studio 2012, asígnele el nombre `OrderProcessing`.

2. Agregue un nuevo proyecto de aplicación de servicio de flujo de trabajo WCF denominado `OrderService` a la solución.

3. En el cuadro de diálogo Propiedades del proyecto, seleccione la pestaña **Web** .

    1. En **acción de inicio** , seleccione **página específica** y especifique `Service1.xamlx`.

        ![Propiedades web del proyecto de servicio de flujo de trabajo](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "Crear la opción de página específica del servicio de flujo de trabajo hospedado en Web")

    2. En **servidores** , seleccione **usar servidor Web de IIS local**.

        ![Configuración del servidor Web local](./media/creating-a-long-running-workflow-service/use-local-web-server.png "Crear el servicio de flujo de trabajo hospedado en Web: usar la opción de servidor Web de IIS local")

        > [!WARNING]
        > Debe ejecutar Visual Studio 2012 en modo de administrador para establecer esta configuración.

        Estos dos pasos configuran el proyecto de servicio de flujo de trabajo que IIS va a hospedar.

4. Abra `Service1.xamlx` si aún no está abierto y elimine las actividades **ReceiveRequest** y **SendResponse** existentes.

5. Seleccione la actividad de **servicio secuencial** y haga clic en el vínculo **variables** y agregue las variables que se muestran en la siguiente ilustración. De esta forma, se agregan algunas variables que se usarán posteriormente en el servicio de flujo de trabajo.

    > [!NOTE]
    > Si CorrelationHandle no está en la lista desplegable tipo de variable, seleccione **Buscar tipos** en la lista desplegable. Escriba CorrelationHandle en el cuadro **nombre de tipo** , seleccione CorrelationHandle en el cuadro de lista y haga clic en **Aceptar**.

    ![Agregar variables](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "Agregar variables a la actividad de servicio secuencial.")

6. Arrastre y coloque una plantilla de actividad **ReceiveAndSendReply** en la actividad de **servicio secuencial** . Este conjunto de actividades recibirá un mensaje de un cliente y devolverá un respuesta.

    1. Seleccione la actividad **Receive** y establezca las propiedades resaltadas en la siguiente ilustración.

        ![Establecer propiedades de la actividad Receive](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "Establezca las propiedades de la actividad Receive.")

        La propiedad DisplayName establece el nombre mostrado para la actividad Receive en el diseñador. Las propiedades ServiceContractName y OperationName especifican el nombre del contrato de servicio y la operación que implementa la actividad Receive. Para obtener más información sobre cómo se usan los contratos en los servicios de flujo de trabajo, vea [usar contratos en el flujo de trabajo](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).

    2. Haga clic en el vínculo **definir...** en la actividad **ReceiveStartOrder** y establezca las propiedades que se muestran en la siguiente ilustración.  Observe que el botón de radio **parámetros** está seleccionado, un parámetro denominado `p_customerName` está enlazado a la variable `customerName`. Esto configura la actividad **Receive** para recibir algunos datos y enlazarlos a las variables locales.

        ![Establecer los datos recibidos por la actividad Receive](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "Establezca las propiedades de los datos recibidos por la actividad Receive.")

    3. Seleccione la actividad **SendReplyToReceive** y establezca la propiedad resaltada que se muestra en la siguiente ilustración.

        ![Establecer las propiedades de la actividad SendReply](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")

    4. Haga clic en el vínculo **definir...** en la actividad **SendReplyToStartOrder** y establezca las propiedades que se muestran en la siguiente ilustración. Observe que el botón de radio **parámetros** está seleccionado; un parámetro denominado `p_orderId` se enlaza a la variable `orderId`. Esta configuración especifica que la actividad SendReplyToStartOrder ejecutará un valor de tipo de cadena en el autor de la llamada.

        ![Configurar los datos de contenido de la actividad SendReply](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "Configurar la opción para la actividad SetReplyToStartOrder.")

    5. Arrastre y coloque una actividad Assign entre las actividades **Receive** y **SendReply** y establezca las propiedades como se muestra en la siguiente ilustración:

        ![Agregar una actividad Assign](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "Agregue una actividad Assign.")

        De esta forma, se crea un identificador de nuevo pedido y se coloca el valor en la variable orderId.

    6. Seleccione la actividad **ReplyToStartOrder** . En la ventana Propiedades, haga clic en el botón de puntos suspensivos de **CorrelationInitializers**. Seleccione el vínculo **Agregar inicializador** , escriba `orderIdHandle` en el cuadro de texto inicializador, seleccione inicializador de correlación de consulta para el tipo de correlación y seleccione p_orderId en el cuadro desplegable consultas XPath. Esta configuración se muestra en la siguiente ilustración. Haga clic en **Aceptar**.  De esta forma, se inicializa una correlación entre el cliente y esta instancia del servicio de flujo de trabajo. Cuando se reciba un mensaje con este identificador de pedido, se enruta a esta instancia del servicio de flujo de trabajo.

        ![Agregar un inicializador de correlación](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "Agregue un inicializador de correlación.")

7. Arrastre y coloque otra actividad **ReceiveAndSendReply** al final del flujo de trabajo (fuera de la **secuencia** que contiene las actividades **Receive** y **SendReply** ). De esta forma, se recibirá el segundo mensaje enviado por el cliente y se responderá al mismo.

    1. Seleccione la **secuencia** que contiene las actividades **Receive** y **SendReply** recién agregadas y haga clic en el botón **variables** . Agregue la variable resaltada en la siguiente ilustración:

        ![Agregar nuevas variables](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "Agregue la variable ItemId.")

        Agregue también `orderResult` como **cadena** en el ámbito de `Sequence`.

    2. Seleccione la actividad **Receive** y establezca las propiedades que se muestran en la siguiente ilustración:

        ![Establecer las propiedades de la actividad Receive](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "Establezca las propiedades de las actividades de recepción.")

        > [!NOTE]
        > No olvide cambiar el campo **ServiceContractName** por `../IAddItem`.

    3. Haga clic en el vínculo **definir...** en la actividad **ReceiveAddItem** y agregue los parámetros que se muestran en la siguiente ilustración: Esto configura la actividad Receive para aceptar dos parámetros, el identificador de pedido y el identificador del elemento que se está ordenando.

        ![Especificar parámetros para la segunda recepción](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "Configure la actividad Receive para recibir dos parámetros.")

    4. Haga clic en el botón de puntos suspensivos **CorrelateOn** y escriba `orderIdHandle`. En **consultas XPath**, haga clic en la flecha desplegable y seleccione `p_orderId`. De esta forma, se configura la correlación de la segunda actividad de recepción. Para obtener más información sobre la correlación, vea [correlación](../../../../docs/framework/wcf/feature-details/correlation.md).

        ![Establecimiento de la propiedad CorrelatesOn](./media/creating-a-long-running-workflow-service/correlateson-setting.png "Establezca la propiedad CorrelatesOn.")

    5. Arrastre y coloque una actividad **If** inmediatamente después de la actividad **ReceiveAddItem** . Esta actividad actúa como instrucción If.

        1. Establezca la propiedad **Condition** en `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`

        2. Arrastre y coloque una actividad **assign** en la sección **then** y otra en la sección **else** y establezca las propiedades de las actividades de **asignación** tal como se muestra en la siguiente ilustración.

            ![Asignar el resultado de la llamada de servicio](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "Asigne el resultado de la llamada de servicio.")

            Si la condición es `true` se ejecutará la sección **then** . Si la condición es `false` se ejecuta la sección **else** .

        3. Seleccione la actividad **SendReplyToReceive** y establezca la propiedad **displayName** que se muestra en la siguiente ilustración.

            ![Establecer las propiedades de la actividad SendReply](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "Establezca la propiedad de actividad SendReply.")

        4. Haga clic en el vínculo **definir...** en la actividad **SetReplyToAddItem** y configúrelo como se muestra en la siguiente ilustración. Esto configura la actividad **SendReplyToAddItem** para devolver el valor de la variable `orderResult`.

            ![Establecer el enlace de datos para la actividad SendReply](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "Establezca la propiedad para la actividad SendReplyToAddItem.")

8. Abra el archivo Web. config y agregue los siguientes elementos en la sección > de comportamiento de \<para habilitar la persistencia del flujo de trabajo.

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    > Asegúrese de reemplazar el nombre del host y de la instancia de SQL Server en el fragmento de código anterior.

9. Compile la solución.

## <a name="create-a-client-application-to-call-the-workflow-service"></a>Creación de una aplicación cliente para llamar al servicio de flujo de trabajo

1. Agregue un nuevo proyecto de aplicación de consola denominado `OrderClient` a la solución.

2. Agregue referencias a los siguientes ensamblados al proyecto `OrderClient`

    1. System.ServiceModel.dll

    2. System.ServiceModel.Activities.dll

3. Agregue una referencia de servicio al servicio de flujo de trabajo y especifique `OrderService` como el espacio de nombres.

4. En el método `Main()` del proyecto de cliente, agregue el siguiente código:

    ```csharp
    static void Main(string[] args)
    {
       // Send initial message to start the workflow service
       Console.WriteLine("Sending start message");
       StartOrderClient startProxy = new StartOrderClient();
       string orderId = startProxy.StartOrder("Kim Abercrombie");

       // The workflow service is now waiting for the second message to be sent
       Console.WriteLine("Workflow service is idle...");
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");
       Console.ReadLine();

       // Send the second message
       Console.WriteLine("Sending add item message");
       AddItemClient addProxy = new AddItemClient();
       AddItem item = new AddItem();
       item.p_itemId = "Zune HD";
       item.p_orderId = orderId;

       string orderResult = addProxy.AddItem(item);
       Console.WriteLine("Service returned: " + orderResult);
    }
    ```

5. Compile la solución y ejecute la aplicación `OrderClient`. El cliente mostrará un texto similar al siguiente:

    ```output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6. Para comprobar que el servicio de flujo de trabajo se ha guardado, inicie el SQL Server Management Studio; para ello, vaya al menú **Inicio** , seleccione **todos los programas**, **Microsoft SQL Server 2008** **SQL Server Management Studio**.

    1. En el panel izquierdo, expanda **, bases de datos**, **SQLPersistenceStore**, **vistas** y haga clic con el botón secundario en **System. Activities. DurableInstancing. instances** y seleccione **seleccionar las primeras 1000 filas**. En el panel de **resultados** , compruebe que ve al menos una instancia en la lista. Puede que haya otras instancia de ejecuciones previas si se produjo una excepción durante la ejecución. Puede eliminar las filas existentes haciendo clic con el botón secundario en **System. Activities. DurableInstancing. instances** y seleccionando **editar las primeras 200 filas**, presionando el botón **Ejecutar** , seleccionando todas las filas en el panel de resultados y seleccionando **eliminar**.  Para comprobar que la instancia que se muestra en la base de datos es la instancia de la aplicación creada, compruebe que la vista de instancias esté vacía antes de ejecutar el cliente. Una vez que se ejecute el cliente, vuelva a ejecutar la consulta (Seleccionar las primeras 1000 filas) y compruebe que se haya agregado una nueva instancia.

7. Presione Entrar para enviar y agregar un mensaje de elemento al servicio de flujo de trabajo. El cliente mostrará un texto similar al siguiente:

    ```output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
