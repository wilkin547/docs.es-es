---
title: "Recepción almacenada en búfer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b4851425609936d093762895cef6bdbc8ad7823
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="buffered-receive"></a><span data-ttu-id="00220-102">Recepción almacenada en búfer</span><span class="sxs-lookup"><span data-stu-id="00220-102">Buffered Receive</span></span>
<span data-ttu-id="00220-103">En este ejemplo se muestra cómo preparar y configurar la característica de recepción almacenada en búfer en [!INCLUDE[wf](../../../../includes/wf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00220-103">This sample demonstrates how to set up and configure the buffered receive feature in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span> <span data-ttu-id="00220-104">La recepción almacenada en búfer permite al autor del flujo de trabajo crear un flujo de trabajo sin tener que preocuparse por el orden en el que se reciben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="00220-104">Buffered receive allows the workflow author to create a workflow without having to worry about the order in which messages are received.</span></span> <span data-ttu-id="00220-105">Este tipo de recepción almacena en búfer los mensajes localmente y los entrega cuando el flujo de trabajo está listo para recibirlos.</span><span class="sxs-lookup"><span data-stu-id="00220-105">The buffered receive feature buffers messages locally and delivers them when the workflow is ready to receive them.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="00220-106">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="00220-106">Demonstrates</span></span>  
 <span data-ttu-id="00220-107">Procesamiento desordenado de mensajes utilizando la recepción almacenada en búfer con actividades de mensajería.</span><span class="sxs-lookup"><span data-stu-id="00220-107">Out-of-order message processing using buffered receive with messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="00220-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="00220-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="00220-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="00220-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="00220-110">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00220-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="00220-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="00220-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a><span data-ttu-id="00220-112">Explicación</span><span class="sxs-lookup"><span data-stu-id="00220-112">Discussion</span></span>  
 <span data-ttu-id="00220-113">En este ejemplo, un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se implementa utilizando [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y tiene una secuencia de las actividades <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="00220-113">In this sample, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service is implemented using [!INCLUDE[wf1](../../../../includes/wf1-md.md)] and has a sequence of <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="00220-114">Este flujo de trabajo modela un proceso de aprobación de préstamos simple en el que el flujo de trabajo espera tres notificaciones para que se apruebe un préstamo.</span><span class="sxs-lookup"><span data-stu-id="00220-114">This workflow models a simple loan approval process where the workflow expects three notifications for a loan to be approved.</span></span> <span data-ttu-id="00220-115">Una aplicación cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] envía tres notificaciones puestas en correlación en el orden inverso al que el servicio espera.</span><span class="sxs-lookup"><span data-stu-id="00220-115">A [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client application sends three correlated notifications in the reverse order of what the service expects.</span></span> <span data-ttu-id="00220-116">Dado que la característica de recepción almacenada en búfer está activada en el servicio, cada mensaje desordenado se almacena en búfer en el servicio y se procesa cuando el flujo de trabajo está listo para recibirlo.</span><span class="sxs-lookup"><span data-stu-id="00220-116">Because the buffered receive feature is turned on at the service, each out-of-order message is buffered at the service and processed as the workflow becomes ready to receive it.</span></span>  
  
 <span data-ttu-id="00220-117">La característica de recepción almacenada en búfer requiere la compatibilidad con <xref:System.ServiceModel.Activities.ReceiveContent> por parte del enlace; por consiguiente, el servicio utiliza <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="00220-117">The buffered receive feature requires <xref:System.ServiceModel.Activities.ReceiveContent> support from the binding, therefore the service uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="00220-118">No se requiere ninguna configuración especial para el enlace, por lo que se utilizan los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="00220-118">No special configuration is required for the binding, so the defaults are used.</span></span>  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 <span data-ttu-id="00220-119">El servicio también expone metadatos para el servicio utilizando <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="00220-119">The service also exposes metadata for the service using <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span></span>  
  
 <span data-ttu-id="00220-120">De igual forma, el extremo del cliente se configura utilizando <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="00220-120">Similarly, the client endpoint is configured using <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="00220-121">El código de cliente y la configuración se genera mediante el **Agregar referencia de servicio** característica de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00220-121">The client code and configuration is generated by using the **Add Service Reference** feature of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="00220-122">El siguiente ejemplo muestra el extremo de cliente generado en el archivo App.config.</span><span class="sxs-lookup"><span data-stu-id="00220-122">The following example is the generated client endpoint in the App.config file.</span></span>  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 <span data-ttu-id="00220-123">En este ejemplo se requiere que los siguientes componentes de Windows estén habilitados:</span><span class="sxs-lookup"><span data-stu-id="00220-123">This sample requires that the following Windows components are enabled:</span></span>  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]<span data-ttu-id="00220-124"> Compatibilidad con la administración, Metabase y Compatibilidad con la configuración</span><span class="sxs-lookup"><span data-stu-id="00220-124"> Management Compatibility, Metabase, and Configuration Compatibility</span></span>  
  
3.  <span data-ttu-id="00220-125">Servicios World Wide Web, Características de desarrollo de aplicaciones y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="00220-125">World Wide Web Services, Application Development Features, and ASP.NET</span></span>  
  
4.  <span data-ttu-id="00220-126">Microsoft Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="00220-126">Microsoft Message Queues (MSMQ) Server</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="00220-127">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="00220-127">To set up, and build the sample</span></span>  
  
1.  <span data-ttu-id="00220-128">En un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], registre ASP.NET escribiendo `aspnet_regiis –I` y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="00220-128">At a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by typing `aspnet_regiis –I` and press ENTER.</span></span>  
  
2.  <span data-ttu-id="00220-129">Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] como administrador.</span><span class="sxs-lookup"><span data-stu-id="00220-129">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an Administrator.</span></span>  
  
3.  <span data-ttu-id="00220-130">Abra LoanService.sln.</span><span class="sxs-lookup"><span data-stu-id="00220-130">Open LoanService.sln.</span></span>  
  
4.  <span data-ttu-id="00220-131">Cuando se le pregunte si desea crear los directorios virtuales del proyecto LoanService, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="00220-131">When asked if you would like to create the virtual directories for the LoanService project, select **Yes**.</span></span>  
  
#### <a name="to-set-up-the-service-queues"></a><span data-ttu-id="00220-132">Para configurar las colas de servicio</span><span class="sxs-lookup"><span data-stu-id="00220-132">To set up the service queues</span></span>  
  
1.  <span data-ttu-id="00220-133">Presione F5 para ejecutar la aplicación LoanClient que crea las colas y activa el servicio definido en Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="00220-133">Press F5 to run the LoanClient application that creates the queues and activates the service defined in Service1.xamlx.</span></span>  
  
2.  <span data-ttu-id="00220-134">Abra la **administración de equipos** consola ejecutando Compmgmt.msc desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="00220-134">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
3.  <span data-ttu-id="00220-135">En el **administración de equipos** de la consola, expanda **servicio**, **aplicaciones**, **Message Queue Server**, **colas privadas** .</span><span class="sxs-lookup"><span data-stu-id="00220-135">In the **Computer Management** console, expand **Service**, **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
4.  <span data-ttu-id="00220-136">Haga clic en la cola loanservice/Service1.xamlx y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="00220-136">Right-click the loanservice/service1.xamlx queue and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="00220-137">Seleccione el **seguridad** pestaña y agregar **todos reciben mensaje**, **Inspeccionar mensaje** y **enviar mensaje** permisos.</span><span class="sxs-lookup"><span data-stu-id="00220-137">Select the **Security** tab, and add **Everyone Receives Message**, **Peek Message** and **Send Message** permissions.</span></span>  
  
6.  <span data-ttu-id="00220-138">Abra el Administrador de [!INCLUDE[iis60](../../../../includes/iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00220-138">Open the [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Manager.</span></span>  
  
7.  <span data-ttu-id="00220-139">Vaya a **Server**, **sitios**, **sitio Web predeterminado**, **privada**, **LoanService** y seleccione  **Opciones avanzadas**</span><span class="sxs-lookup"><span data-stu-id="00220-139">Browse to **Server**, **Sites**, **Default Web site**, **Private**, **LoanService** and select **Advanced Options**</span></span>  
  
8.  <span data-ttu-id="00220-140">Cambiar el **protocolos habilitados** como **http**, **net.msmq**.</span><span class="sxs-lookup"><span data-stu-id="00220-140">Change the **Enabled Protocols** to be **http**, **net.msmq**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="00220-141">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="00220-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="00220-142">Vaya a http://localhost/private/loanservice/service1.xamlx para asegurarse de que el servicio se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="00220-142">Browse to http://localhost/private/loanservice/service1.xamlx to ensure that the service is running.</span></span>  
  
2.  <span data-ttu-id="00220-143">Presione F5 para ejecutar la aplicación LoanClient.</span><span class="sxs-lookup"><span data-stu-id="00220-143">Press F5 to run the LoanClient application.</span></span> <span data-ttu-id="00220-144">Cuando el flujo de trabajo finaliza, se debe guardar un archivo out.txt en C:\Inbox que contenga el resultado del intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="00220-144">Once the workflow is complete, an out.txt file should be saved to C:\Inbox that contains the result of the message exchange.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="00220-145">Para realizar una limpieza</span><span class="sxs-lookup"><span data-stu-id="00220-145">To clean up</span></span>  
  
1.  <span data-ttu-id="00220-146">Abra la **administración de equipos** consola ejecutando Compmgmt.msc desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="00220-146">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
2.  <span data-ttu-id="00220-147">Expanda **servicio** y **aplicaciones**, **Message Queue Server**, **colas privadas**.</span><span class="sxs-lookup"><span data-stu-id="00220-147">Expand **Service** and **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="00220-148">Elimine la cola loanservice/service1 .xamlx.</span><span class="sxs-lookup"><span data-stu-id="00220-148">Delete the loanservice/service1.xamlx queue.</span></span>  
  
4.  <span data-ttu-id="00220-149">Quite el directorio C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="00220-149">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="00220-150">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="00220-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="00220-151">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="00220-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="00220-152">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00220-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="00220-153">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="00220-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
