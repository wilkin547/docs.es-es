---
title: Recepción almacenada en búfer
ms.date: 03/30/2017
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
ms.openlocfilehash: b95577c71493275f30703b4366fab32a51097bd2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526809"
---
# <a name="buffered-receive"></a><span data-ttu-id="e9909-102">Recepción almacenada en búfer</span><span class="sxs-lookup"><span data-stu-id="e9909-102">Buffered Receive</span></span>
<span data-ttu-id="e9909-103">Este ejemplo muestra cómo instalar y configurar la característica de recepción almacenada en búfer en Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="e9909-103">This sample demonstrates how to set up and configure the buffered receive feature in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="e9909-104">La recepción almacenada en búfer permite al autor del flujo de trabajo crear un flujo de trabajo sin tener que preocuparse por el orden en el que se reciben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e9909-104">Buffered receive allows the workflow author to create a workflow without having to worry about the order in which messages are received.</span></span> <span data-ttu-id="e9909-105">Este tipo de recepción almacena en búfer los mensajes localmente y los entrega cuando el flujo de trabajo está listo para recibirlos.</span><span class="sxs-lookup"><span data-stu-id="e9909-105">The buffered receive feature buffers messages locally and delivers them when the workflow is ready to receive them.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="e9909-106">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="e9909-106">Demonstrates</span></span>  
 <span data-ttu-id="e9909-107">Procesamiento desordenado de mensajes utilizando la recepción almacenada en búfer con actividades de mensajería.</span><span class="sxs-lookup"><span data-stu-id="e9909-107">Out-of-order message processing using buffered receive with messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9909-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e9909-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e9909-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e9909-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e9909-110">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e9909-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e9909-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e9909-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a><span data-ttu-id="e9909-112">Explicación</span><span class="sxs-lookup"><span data-stu-id="e9909-112">Discussion</span></span>  
 <span data-ttu-id="e9909-113">En este ejemplo, un servicio de Windows Communication Foundation (WCF) se implementa mediante [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y tiene una secuencia de <xref:System.ServiceModel.Activities.Receive> actividades.</span><span class="sxs-lookup"><span data-stu-id="e9909-113">In this sample, a Windows Communication Foundation (WCF) service is implemented using [!INCLUDE[wf1](../../../../includes/wf1-md.md)] and has a sequence of <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="e9909-114">Este flujo de trabajo modela un proceso de aprobación de préstamos simple en el que el flujo de trabajo espera tres notificaciones para que se apruebe un préstamo.</span><span class="sxs-lookup"><span data-stu-id="e9909-114">This workflow models a simple loan approval process where the workflow expects three notifications for a loan to be approved.</span></span> <span data-ttu-id="e9909-115">Una aplicación de cliente de Windows Communication Foundation (WCF) envía tres notificaciones correlacionadas en el orden inverso de lo que espera el servicio.</span><span class="sxs-lookup"><span data-stu-id="e9909-115">A Windows Communication Foundation (WCF) client application sends three correlated notifications in the reverse order of what the service expects.</span></span> <span data-ttu-id="e9909-116">Dado que la característica de recepción almacenada en búfer está activada en el servicio, cada mensaje desordenado se almacena en búfer en el servicio y se procesa cuando el flujo de trabajo está listo para recibirlo.</span><span class="sxs-lookup"><span data-stu-id="e9909-116">Because the buffered receive feature is turned on at the service, each out-of-order message is buffered at the service and processed as the workflow becomes ready to receive it.</span></span>  
  
 <span data-ttu-id="e9909-117">La característica de recepción almacenada en búfer requiere la compatibilidad con <xref:System.ServiceModel.Activities.ReceiveContent> por parte del enlace; por consiguiente, el servicio utiliza <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="e9909-117">The buffered receive feature requires <xref:System.ServiceModel.Activities.ReceiveContent> support from the binding, therefore the service uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="e9909-118">No se requiere ninguna configuración especial para el enlace, por lo que se utilizan los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e9909-118">No special configuration is required for the binding, so the defaults are used.</span></span>  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 <span data-ttu-id="e9909-119">El servicio también expone metadatos para el servicio utilizando <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="e9909-119">The service also exposes metadata for the service using <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span></span>  
  
 <span data-ttu-id="e9909-120">De igual forma, el extremo del cliente se configura utilizando <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="e9909-120">Similarly, the client endpoint is configured using <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="e9909-121">Se genera el código de cliente y la configuración mediante el **Add Service Reference** característica de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e9909-121">The client code and configuration is generated by using the **Add Service Reference** feature of Visual Studio.</span></span> <span data-ttu-id="e9909-122">El siguiente ejemplo muestra el extremo de cliente generado en el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="e9909-122">The following example is the generated client endpoint in the App.config file.</span></span>  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 <span data-ttu-id="e9909-123">En este ejemplo se requiere que los siguientes componentes de Windows estén habilitados:</span><span class="sxs-lookup"><span data-stu-id="e9909-123">This sample requires that the following Windows components are enabled:</span></span>  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]<span data-ttu-id="e9909-124"> Compatibilidad con la administración, Metabase y Compatibilidad con la configuración</span><span class="sxs-lookup"><span data-stu-id="e9909-124"> Management Compatibility, Metabase, and Configuration Compatibility</span></span>  
  
3.  <span data-ttu-id="e9909-125">Servicios World Wide Web, Características de desarrollo de aplicaciones y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e9909-125">World Wide Web Services, Application Development Features, and ASP.NET</span></span>  
  
4.  <span data-ttu-id="e9909-126">Microsoft Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="e9909-126">Microsoft Message Queues (MSMQ) Server</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="e9909-127">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9909-127">To set up, and build the sample</span></span>  
  
1.  <span data-ttu-id="e9909-128">En un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], registre ASP.NET escribiendo `aspnet_regiis –I` y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="e9909-128">At a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by typing `aspnet_regiis –I` and press ENTER.</span></span>  
  
2.  <span data-ttu-id="e9909-129">Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] como administrador.</span><span class="sxs-lookup"><span data-stu-id="e9909-129">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an Administrator.</span></span>  
  
3.  <span data-ttu-id="e9909-130">Abra LoanService.sln.</span><span class="sxs-lookup"><span data-stu-id="e9909-130">Open LoanService.sln.</span></span>  
  
4.  <span data-ttu-id="e9909-131">Cuando se le pregunte si desea crear los directorios virtuales del proyecto LoanService, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e9909-131">When asked if you would like to create the virtual directories for the LoanService project, select **Yes**.</span></span>  
  
#### <a name="to-set-up-the-service-queues"></a><span data-ttu-id="e9909-132">Para configurar las colas de servicio</span><span class="sxs-lookup"><span data-stu-id="e9909-132">To set up the service queues</span></span>  
  
1.  <span data-ttu-id="e9909-133">Presione F5 para ejecutar la aplicación LoanClient que crea las colas y activa el servicio definido en Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="e9909-133">Press F5 to run the LoanClient application that creates the queues and activates the service defined in Service1.xamlx.</span></span>  
  
2.  <span data-ttu-id="e9909-134">Abra el **administración de equipos** consola ejecutando Compmgmt.msc desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e9909-134">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
3.  <span data-ttu-id="e9909-135">En el **administración de equipos** de consola, expanda **servicio**, **aplicaciones**, **Message Queue Server**, **colas privadas** .</span><span class="sxs-lookup"><span data-stu-id="e9909-135">In the **Computer Management** console, expand **Service**, **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
4.  <span data-ttu-id="e9909-136">Haga clic en la cola loanservice/Service1.xamlx y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e9909-136">Right-click the loanservice/service1.xamlx queue and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="e9909-137">Seleccione el **seguridad** y agregar **todos reciben mensaje**, **Inspeccionar mensaje** y **enviar mensaje** permisos.</span><span class="sxs-lookup"><span data-stu-id="e9909-137">Select the **Security** tab, and add **Everyone Receives Message**, **Peek Message** and **Send Message** permissions.</span></span>  
  
6.  <span data-ttu-id="e9909-138">Abra el Administrador de [!INCLUDE[iis60](../../../../includes/iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9909-138">Open the [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Manager.</span></span>  
  
7.  <span data-ttu-id="e9909-139">Vaya a **Server**, **sitios**, **sitio Web predeterminado**, **privada**, **LoanService** y seleccione  **Opciones avanzadas**</span><span class="sxs-lookup"><span data-stu-id="e9909-139">Browse to **Server**, **Sites**, **Default Web site**, **Private**, **LoanService** and select **Advanced Options**</span></span>  
  
8.  <span data-ttu-id="e9909-140">Cambiar el **protocolos habilitados** sea **http**, **net.msmq**.</span><span class="sxs-lookup"><span data-stu-id="e9909-140">Change the **Enabled Protocols** to be **http**, **net.msmq**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="e9909-141">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9909-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="e9909-142">Vaya a http://localhost/private/loanservice/service1.xamlx para asegurarse de que el servicio se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="e9909-142">Browse to http://localhost/private/loanservice/service1.xamlx to ensure that the service is running.</span></span>  
  
2.  <span data-ttu-id="e9909-143">Presione F5 para ejecutar la aplicación LoanClient.</span><span class="sxs-lookup"><span data-stu-id="e9909-143">Press F5 to run the LoanClient application.</span></span> <span data-ttu-id="e9909-144">Cuando el flujo de trabajo finaliza, se debe guardar un archivo out.txt en C:\Inbox que contenga el resultado del intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="e9909-144">Once the workflow is complete, an out.txt file should be saved to C:\Inbox that contains the result of the message exchange.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="e9909-145">Para realizar una limpieza</span><span class="sxs-lookup"><span data-stu-id="e9909-145">To clean up</span></span>  
  
1.  <span data-ttu-id="e9909-146">Abra el **administración de equipos** consola ejecutando Compmgmt.msc desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e9909-146">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
2.  <span data-ttu-id="e9909-147">Expanda **servicio** y **aplicaciones**, **Message Queue Server**, **colas privadas**.</span><span class="sxs-lookup"><span data-stu-id="e9909-147">Expand **Service** and **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="e9909-148">Elimine la cola loanservice/service1 .xamlx.</span><span class="sxs-lookup"><span data-stu-id="e9909-148">Delete the loanservice/service1.xamlx queue.</span></span>  
  
4.  <span data-ttu-id="e9909-149">Quite el directorio C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="e9909-149">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9909-150">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e9909-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e9909-151">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e9909-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e9909-152">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e9909-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e9909-153">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e9909-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
