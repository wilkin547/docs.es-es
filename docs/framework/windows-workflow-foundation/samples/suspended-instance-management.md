---
title: Administración de instancias suspendidas
ms.date: 03/30/2017
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
ms.openlocfilehash: 3f1f4f8edcbe0e05067d3ca739ef3d5f4fe4d798
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715941"
---
# <a name="suspended-instance-management"></a>Administración de instancias suspendidas
En este ejemplo se muestra cómo administrar instancias de flujo de trabajo que se han suspendido.  La acción predeterminada para <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es `AbandonAndSuspend`. Esto significa que, de forma predeterminada, las excepciones no controladas producidas por una instancia de flujo de trabajo hospedada en <xref:System.ServiceModel.WorkflowServiceHost> causarán que la instancia se elimine de la memoria (se abandone) y la versión duradera/conservada de la instancia se marque como suspendida. Una instancia de flujo de trabajo suspendida no se podrá ejecutar hasta que no se anule la suspensión.

 El ejemplo muestra cómo se puede implementar una utilidad de línea de comandos para consultar las instancias suspendidas y cómo otorgarle al usuario la opción de reanudar o finalizar la instancia. En este ejemplo, un servicio de flujo de trabajo produce una excepción de forma intencionada, haciendo que se suspenda. La utilidad de línea de comandos se puede utilizar a continuación para consultar la instancia y reanudarla o finalizarla.

## <a name="demonstrates"></a>Demostraciones
 <xref:System.ServiceModel.WorkflowServiceHost> con <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> y <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> en Windows Workflow Foundation (WF).

## <a name="discussion"></a>Discusión
 La utilidad de línea de comandos implementada en este ejemplo es específica de la implementación del almacén de instancias de SQL que se distribuye con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Si tiene una implementación personalizada del almacén de instancias, podrá adaptar esta utilidad reemplazando las implementaciones de `WorkflowInstanceCommand` en el ejemplo con implementaciones que sean específicas de su almacén de instancias.

 La implementación proporcionada ejecuta directamente comandos SQL en el almacén de instancias de SQL para enumerar las instancias suspendidas y se basa en un objeto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> agregado al host <xref:System.ServiceModel.WorkflowServiceHost> para reanudar o finalizar las instancias.

#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. En este ejemplo se requiere que los siguientes componentes de Windows estén habilitados:

    1. Microsoft Message Queuing (MSMQ)

    2. SQL Server Express

2. Configure la base de datos de SQL Server.

    1. En un símbolo del sistema de Visual Studio 2010, ejecute "Setup. cmd" desde el directorio de ejemplo SuspendedInstanceManagement, que hace lo siguiente:

        1. Crea una base de datos de persistencia mediante SQL Server Express. Si la base de datos de persistencia ya existe, se quita y se vuelve a crear.

        2. Configura la base de datos para la persistencia.

        3. Agrega IIS APPPOOL\DefaultAppPool y NT AUTHORITY\Network Service al rol InstanceStoreUsers que se definió al configurar la base de datos para la persistencia.

3. Configure la cola del servicio.

    1. En Visual Studio 2010, haga clic con el botón derecho en el proyecto **SampleWorkflowApp** y haga clic en **establecer como proyecto de inicio**.

    2. Compile y ejecute SampleWorkflowApp presionando **F5**. Esto creará la cola necesaria.

    3. Presione **entrar** para detener el SampleWorkflowApp.

    4. En un símbolo del sistema, ejecute Compmgmt.msc para abrir la consola Administración de equipos.

    5. Expanda **servicios y aplicaciones**, **Message Queue Server**, **colas privadas**.

    6. Haga clic con el botón derecho en la cola **ReceiveTx** y seleccione **propiedades**.

    7. Seleccione la **pestaña seguridad** y permita **que todos** tengan permisos para **recibir mensajes**, **Inspeccionar mensaje**y **Enviar mensaje**.

4. Ejecute el ejemplo.

    1. En Visual Studio 2010, vuelva a ejecutar el proyecto SampleWorkflowApp sin depurar presionando **Ctrl + F5**. En la ventana de la consola se imprimirán dos direcciones de extremo: una para el extremo de la aplicación y otra procedente de <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>. A continuación, se crea una instancia de flujo de trabajo y en la ventana de la consola aparecerán los registros de seguimiento de esa instancia. La instancia de flujo de trabajo producirá una excepción que hará que la instancia se suspenda y se anule.

    2. La utilidad de línea de comandos se puede utilizar a continuación para realizar más acciones en cualquiera de estas instancias. La sintaxis para los argumentos de la línea de comandos es la siguiente:

         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`

         Los comandos admitidos son: `Query`, `Resume` y `Terminate`.  El modificador InstanceId solo es necesario para las operaciones `Resume` y `Terminate`.

#### <a name="to-cleanup-optional"></a>Para realizar la limpieza (Opcional)

1. En un símbolo del sistema de `vs2010`, ejecute Compmgmt.msc para abrir la consola Administración de equipos.

2. Expanda **servicios y aplicaciones**, **Message Queue Server**, **colas privadas**.

3. Elimine la cola **ReceiveTx** .

4. Para quitar la base de datos de persistencia, ejecute cleanup.cmd.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
