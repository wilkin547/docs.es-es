---
title: "Dúplex duradero"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d8beae85b2cee8956efd160b8540e76f04dd7ee7
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="durable-duplex"></a><span data-ttu-id="a7226-102">Dúplex duradero</span><span class="sxs-lookup"><span data-stu-id="a7226-102">Durable Duplex</span></span>
<span data-ttu-id="a7226-103">En este ejemplo se muestra cómo instalar y configurar el intercambio de mensajes dúplex duradero utilizando las actividades de mensajería de [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7226-103">This sample demonstrates how to set up and configure durable duplex message exchange using the messaging activities in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span> <span data-ttu-id="a7226-104">Un intercambio de mensajes dúplex duradero es un intercambio de mensajes bidireccional que tiene lugar a lo largo de un período largo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="a7226-104">A durable duplex message exchange is a two-way message exchange that takes place over a long period of time.</span></span> <span data-ttu-id="a7226-105">La duración del intercambio de mensajes puede ser mayor que la duración del canal de comunicación y la duración en memoria de las instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="a7226-105">The lifetime of the message exchange may be longer than the lifetime of the communication channel and the in-memory lifetime of the service instances.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="a7226-106">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7226-106">Sample Details</span></span>  
 <span data-ttu-id="a7226-107">En este ejemplo, se configuran dos servicios [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementados utilizando [!INCLUDE[wf2](../../../../includes/wf2-md.md)] para tener un intercambio de mensajes dúplex duradero.</span><span class="sxs-lookup"><span data-stu-id="a7226-107">In this sample, two [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services implemented using [!INCLUDE[wf2](../../../../includes/wf2-md.md)] are configured to have a durable duplex message exchange.</span></span> <span data-ttu-id="a7226-108">El intercambio de mensajes dúplex duradero está compuesto por dos mensajes unidireccionales enviados a través de MSMQ y se correlacionan con [intercambio de contexto de .NET](http://go.microsoft.com/fwlink/?LinkID=166059).</span><span class="sxs-lookup"><span data-stu-id="a7226-108">The durable duplex message exchange is composed from two one-way messages sent over MSMQ and correlated using [.NET Context Exchange](http://go.microsoft.com/fwlink/?LinkID=166059).</span></span> <span data-ttu-id="a7226-109">Los mensajes se envían mediante las actividades de mensajería <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="a7226-109">The messages are sent using the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> messaging activities.</span></span> <span data-ttu-id="a7226-110">El intercambio de contexto de .NET se utiliza para especificar la dirección de devolución de llamada en los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="a7226-110">.NET Context Exchange is use to specify the callback address on the sent messages.</span></span> <span data-ttu-id="a7226-111">Ambos servicios se hospedan mediante Windows Process Activation Services (WAS) y se configuran para habilitar la persistencia de las instancias de los servicios.</span><span class="sxs-lookup"><span data-stu-id="a7226-111">Both services are hosted using Windows Process Activation Services (WAS) and are configured to enable persistence of the services instances.</span></span>  
  
 <span data-ttu-id="a7226-112">El primer servicio (Service1.xamlx) envía una solicitud al servicio de envío (Service2.xamlx) para que realice algún trabajo.</span><span class="sxs-lookup"><span data-stu-id="a7226-112">The first service (Service1.xamlx) sends a request to the send service (Service2.xamlx) to do some work.</span></span> <span data-ttu-id="a7226-113">Una vez completado el trabajo, Service2.xamlx devuelve una notificación a Service1.xamlx para indicar que se ha completado el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a7226-113">Once the work is completed, Service2.xamlx sends a notification back to Service1.xamlx to indicate that the work has been completed.</span></span> <span data-ttu-id="a7226-114">Una aplicación de consola de flujo de trabajo prepara las colas donde están realizando escuchas los servicios y envía al mensaje Start inicial para activar Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a7226-114">A workflow console application sets up the queues that the services are listening on and sends the initial Start message to activate Service1.xamlx.</span></span> <span data-ttu-id="a7226-115">Cuando Service1.xamlx recibe la notificación de Service2.xamlx que indica que se ha completado el trabajo solicitado, Service1.xamlx guarda el resultado en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a7226-115">Once Service1.xamlx receives the notification from Service2.xamlx that the requested work has been completed, Service1.xamlx saves the result to an XML file.</span></span> <span data-ttu-id="a7226-116">Mientras espera el mensaje de devolución de llamada, Service1.xamlx conserva su estado de la instancia mediante la clase <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a7226-116">While waiting for the callback message, Service1.xamlx persists its instance state using the default <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>.</span></span> <span data-ttu-id="a7226-117">Service2.xamlx conserva su estado de instancia como parte de la finalización del trabajo solicitado por Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a7226-117">Service2.xamlx persists its instance state as part of completing the work requested by Service1.xamlx.</span></span>  
  
 <span data-ttu-id="a7226-118">Para configurar los servicios y que usen el intercambio de contexto de .NET en MSMQ, ambos servicios se configuran para utilizar un enlace personalizado que consta de <xref:System.ServiceModel.Channels.ContextBindingElement> y <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="a7226-118">To configure the services to use .NET Context Exchange over MSMQ, both services are configured to use a custom binding that consists of the <xref:System.ServiceModel.Channels.ContextBindingElement> and the <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span></span> <span data-ttu-id="a7226-119">Una dirección de devolución de llamada se especifica con <xref:System.ServiceModel.Channels.ContextBindingElement> y se incluye en un encabezado de contexto de devolución de llamada con todos los mensajes enviados mediante un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a7226-119">A callback address is specified with the <xref:System.ServiceModel.Channels.ContextBindingElement> and is included in a callback context header with all messages sent using a custom binding.</span></span> <span data-ttu-id="a7226-120">El siguiente ejemplo de código define el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a7226-120">The following code example defines the custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="a7226-121">El enlace utilizado por este ejemplo no es seguro.</span><span class="sxs-lookup"><span data-stu-id="a7226-121">The binding used by this sample is not secure.</span></span> <span data-ttu-id="a7226-122">Al implementar su aplicación, debería configurar el enlace en función de los requisitos de seguridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a7226-122">When deploying your application you should configure your binding based on the security requirements of your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7226-123">Las colas utilizadas en este ejemplo no son transaccionales.</span><span class="sxs-lookup"><span data-stu-id="a7226-123">The queues used in this sample are not transactional.</span></span> <span data-ttu-id="a7226-124">Para obtener un ejemplo que muestra cómo configurar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] intercambios que utilizan colas de transacciones de mensajes, consulte el [activación de MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7226-124">For a sample that shows how to set up [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message exchanges using transaction queues, see the [MSMQ Activation](../../../../docs/framework/wcf/samples/msmq-activation.md) sample.</span></span>  
  
 <span data-ttu-id="a7226-125">El mensaje enviado por Service1.xamlx a Service2.xamlx se envía mediante un punto de conexión de cliente configurado con la dirección de Service2.xamlx y el enlace personalizado definido previamente.</span><span class="sxs-lookup"><span data-stu-id="a7226-125">The message sent by Service1.xamlx to Service2.xamlx is sent using a client endpoint configured with the address of Service2.xamlx and the custom binding defined previously.</span></span> <span data-ttu-id="a7226-126">La devolución de llamada de Service2.xamlx a Service1.xamlx se envía mediante un extremo de cliente sin ninguna dirección configurada explícitamente, ya que la dirección se toma del contexto de devolución de llamada enviado por Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a7226-126">The callback from Service2.xamlx to Service1.xamlx is sent using a client endpoint with no explicitly configured address because the address is taken from the callback context sent by Service1.xamlx.</span></span> <span data-ttu-id="a7226-127">El siguiente ejemplo de código define los extremos de cliente.</span><span class="sxs-lookup"><span data-stu-id="a7226-127">The following code example defines the client endpoints.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a7226-128">El siguiente ejemplo de código expone los extremos que usan este enlace personalizado cambiando la asignación de protocolo predeterminado para que las direcciones base de net.msmq utilicen este enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a7226-128">The following code example exposes endpoints using this custom binding by changing the default protocol mapping for net.msmq base addresses to use this custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="a7226-129">El siguiente ejemplo de código habilita la persistencia para ambos servicios agregando el comportamiento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> a ambos servicios y especificando la cadena de conexión para la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="a7226-129">The following code example enables persistence for both services by adding the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior to both services and specifying the connection string for the persistence database.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a><span data-ttu-id="a7226-130">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="a7226-130">System Requirements</span></span>  
 <span data-ttu-id="a7226-131">Este ejemplo requiere los componentes siguientes.</span><span class="sxs-lookup"><span data-stu-id="a7226-131">This sample requires the following components.</span></span>  
  
1.  <span data-ttu-id="a7226-132">Internet Information Services.</span><span class="sxs-lookup"><span data-stu-id="a7226-132">Internet Information Services.</span></span>  
  
2.  <span data-ttu-id="a7226-133">Internet Information Services -> Compatibilidad con la administración de IIS 6.0 -> Compatibilidad con la configuración de metabase de IIS e IIS 6.0.</span><span class="sxs-lookup"><span data-stu-id="a7226-133">Internet Information Services -> IIS 6.0 Management Compatibility -> IIS Metabase and IIS 6.0 configuration compatibility.</span></span>  
  
3.  <span data-ttu-id="a7226-134">Servicios World Wide Web -> Características de desarrollo de aplicaciones -> ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a7226-134">World Wide Web Services -> Application Development Features -> ASP.NET.</span></span>  
  
4.  <span data-ttu-id="a7226-135">Microsoft Message Queues (MSMQ) Server.</span><span class="sxs-lookup"><span data-stu-id="a7226-135">Microsoft Message Queues (MSMQ) Server.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a7226-136">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7226-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="a7226-137">Configure la base de datos de persistencia y el directorio de resultados.</span><span class="sxs-lookup"><span data-stu-id="a7226-137">Set up the persistence database and the results directory.</span></span>  
  
    1.  <span data-ttu-id="a7226-138">Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7226-138">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="a7226-139">Navegue hasta la carpeta de este ejemplo y ejecute Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="a7226-139">Navigate to the folder for this sample and run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="a7226-140">Configure la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="a7226-140">Set up the virtual application.</span></span>  
  
    1.  <span data-ttu-id="a7226-141">Desde un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], registre ASP.NET ejecutando el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a7226-141">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by running the following command.</span></span>  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  <span data-ttu-id="a7226-142">Ejecutar [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos de administrador haciendo clic en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y seleccionando **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a7226-142">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator permissions by right-clicking [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and selecting **Run as administrator**.</span></span>  
  
    3.  <span data-ttu-id="a7226-143">Mediante [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo DurableDuplex.sln.</span><span class="sxs-lookup"><span data-stu-id="a7226-143">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DurableDuplex.sln file.</span></span>  
  
3.  <span data-ttu-id="a7226-144">Configure las colas de servicio.</span><span class="sxs-lookup"><span data-stu-id="a7226-144">Set up the service queues.</span></span>  
  
    1.  <span data-ttu-id="a7226-145">Para ejecutar el cliente de DurableDuplex, presione F5.</span><span class="sxs-lookup"><span data-stu-id="a7226-145">To run the DurableDuplex client, press F5.</span></span>  
  
    2.  <span data-ttu-id="a7226-146">Abra la **administración de equipos** consola ejecutando `Compmgmt.msc` desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7226-146">Open the **Computer Management** console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    3.  <span data-ttu-id="a7226-147">Expanda **aplicaciones de servicio y**, **Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="a7226-147">Expand **Service and Applications**, **Message Queuing**.</span></span> <span data-ttu-id="a7226-148">**Colas privadas**.</span><span class="sxs-lookup"><span data-stu-id="a7226-148">**Private Queues**.</span></span>  
  
    4.  <span data-ttu-id="a7226-149">Haga clic en las colas durableduplex / Service1.xamlx y durableduplex/service2.xamlx y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a7226-149">Right-click the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues and select **Properties**.</span></span>  
  
    5.  <span data-ttu-id="a7226-150">Seleccione el **seguridad** pestaña y permitir **todos los usuarios recibir el mensaje**, **Inspeccionar mensaje** y **enviar mensaje** permisos para ambas colas.</span><span class="sxs-lookup"><span data-stu-id="a7226-150">Select the **Security** tab and allow **Everyone Receive Message**, **Peek Message** and **Send Message** permissions for both queues.</span></span>  
  
    6.  <span data-ttu-id="a7226-151">Abra el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="a7226-151">Open Internet Information Services (IIS) Manager.</span></span>  
  
    7.  <span data-ttu-id="a7226-152">Vaya a **Server**, **sitios**, **sitio Web predeterminado**, **privada**, **dúplex duradero** y seleccione **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="a7226-152">Browse to **Server**, **Sites**, **Default Web site**, **private**, **Durable Duplex** and select **Advanced Options**.</span></span>  
  
    8.  <span data-ttu-id="a7226-153">Cambiar el **protocolos habilitados** a **HTTP, NET.MSMQ**.</span><span class="sxs-lookup"><span data-stu-id="a7226-153">Change the **Enabled Protocols** to **http,net.msmq**.</span></span>  
  
4.  <span data-ttu-id="a7226-154">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7226-154">Run the sample.</span></span>  
  
    1.  <span data-ttu-id="a7226-155">Vaya a http://localhost/private/durableduplex/service1.xamlx y http://localhost/private/durableduplex/service2.xamlx para asegurarse de que ambos servicios se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="a7226-155">Browse to http://localhost/private/durableduplex/service1.xamlx and http://localhost/private/durableduplex/service2.xamlx to ensure that both services are running.</span></span>  
  
    2.  <span data-ttu-id="a7226-156">Presione F5 para ejecutar DurableDuplexClient.</span><span class="sxs-lookup"><span data-stu-id="a7226-156">Press F5 to run DurableDuplexClient.</span></span>  
  
         <span data-ttu-id="a7226-157">Cuando el intercambio de mensajes dúplex duradero se completa, se guarda un archivo result.xml en la carpeta C:\Inbox que contiene el resultado del intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a7226-157">When the durable duplex message exchange completes a result.xml file is saved to the C:\Inbox folder and contains the result of the message exchange.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="a7226-158">Para realizar la limpieza (Opcional)</span><span class="sxs-lookup"><span data-stu-id="a7226-158">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="a7226-159">Ejecute Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="a7226-159">Run Cleanup.cmd.</span></span>  
  
    1.  <span data-ttu-id="a7226-160">Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7226-160">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="a7226-161">Navegue hasta la carpeta de este ejemplo y ejecute Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="a7226-161">Navigate to the folder for this sample and run Cleanup.cmd.</span></span>  
  
2.  <span data-ttu-id="a7226-162">Quite la aplicación virtual para los servicios.</span><span class="sxs-lookup"><span data-stu-id="a7226-162">Remove the virtual application for the services.</span></span>  
  
    1.  <span data-ttu-id="a7226-163">Abra el Administrador de Internet Information Services (IIS) ejecutando `Inetmgr.exe` desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7226-163">Open the Internet Information Services (IIS) Manager by running `Inetmgr.exe` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="a7226-164">Busque el sitio Web predeterminado y quitar el **privada** directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="a7226-164">Browse to the default Web site and remove the **private** virtual directory.</span></span>  
  
3.  <span data-ttu-id="a7226-165">Quite las colas preparadas para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7226-165">Remove the queues set up for this sample.</span></span>  
  
    1.  <span data-ttu-id="a7226-166">Abra la consola de administración de equipos mediante la ejecución de `Compmgmt.msc` desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7226-166">Open the Computer Management console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="a7226-167">Expanda **aplicaciones de servicio y**, **Message Queue Server**, **colas privadas**.</span><span class="sxs-lookup"><span data-stu-id="a7226-167">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    3.  <span data-ttu-id="a7226-168">Elimine las colas durableduplex/service1.xamlx y durableduplex/service2.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a7226-168">Delete the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues.</span></span>  
  
4.  <span data-ttu-id="a7226-169">Quite el directorio C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="a7226-169">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a7226-170">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a7226-170">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a7226-171">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a7226-171">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a7226-172">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7226-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a7226-173">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a7226-173">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`