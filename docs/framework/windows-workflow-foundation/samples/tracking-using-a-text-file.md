---
title: Realizar el seguimiento del uso de un archivo de texto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abb29dc584bbede14adcb396df8cd37a894b6f2f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="tracking-using-a-text-file"></a><span data-ttu-id="bf0da-102">Realizar el seguimiento del uso de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="bf0da-102">Tracking Using a Text File</span></span>
<span data-ttu-id="bf0da-103">En este ejemplo se muestra cómo ampliar el seguimiento en [!INCLUDE[wf](../../../../includes/wf-md.md)] creando un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="bf0da-103">This sample demonstrates how to extend tracking in [!INCLUDE[wf](../../../../includes/wf-md.md)] by creating a custom tracking participant.</span></span> <span data-ttu-id="bf0da-104">Los participantes de seguimiento son clases de .NET Framework que reciben registros de seguimiento del motor en tiempo de ejecución a medida que se emiten.</span><span class="sxs-lookup"><span data-stu-id="bf0da-104">Tracking participants are .NET Framework classes that receive tracking records from the runtime as they are emitted.</span></span> <span data-ttu-id="bf0da-105">Puede crear un participante de seguimiento para transportar los eventos de seguimiento al destino necesario para su escenario.</span><span class="sxs-lookup"><span data-stu-id="bf0da-105">You can create a tracking participant to transport the tracking events to whichever destination is required for your scenario.</span></span> <span data-ttu-id="bf0da-106">Por ejemplo, como parte de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se proporciona el participante de seguimiento de ETW (Seguimiento de eventos para Windows).</span><span class="sxs-lookup"><span data-stu-id="bf0da-106">For example, ETW (Event Tracing for Windows) Tracking Participant is provided as part of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="bf0da-107">El participante de seguimiento de este ejemplo escribe los registros en formato XML en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="bf0da-107">The tracking participant in this sample writes the records in XML format to a text file.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="bf0da-108">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf0da-108">Sample details</span></span>  
 <span data-ttu-id="bf0da-109">Para optimizar la utilidad y solidez del participante de seguimiento, deben completarse algunos pasos adicionales para conectar correctamente el participante de seguimiento al motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bf0da-109">To optimize the usefulness and robustness of your tracking participant, some additional steps must be completed to properly wire the tracking participant to the runtime.</span></span> <span data-ttu-id="bf0da-110">En la siguiente tabla se describen las clases utilizadas en este ejemplo para crear un participante de seguimiento que obedece los procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="bf0da-110">The following table describes the classes used in this sample to create a tracking participant that complies with best practices.</span></span>  
  
|<span data-ttu-id="bf0da-111">Clase</span><span class="sxs-lookup"><span data-stu-id="bf0da-111">Class</span></span>|<span data-ttu-id="bf0da-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf0da-112">Description</span></span>|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|<span data-ttu-id="bf0da-113">Se utiliza una clase <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> para definir la sección de configuración utilizada para configurar el participante de seguimiento de archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="bf0da-113">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> is used to define the configuration section used to configure the text file tracking participant.</span></span> <span data-ttu-id="bf0da-114">Esto permite a los usuarios especificar el destino del archivo de registro utilizando archivos de configuración estándar de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf0da-114">This allows users to specify the destination of the log file using standard .NET Framework configuration files.</span></span>|  
|`TextFileTrackingBehavior`|<span data-ttu-id="bf0da-115">Los comportamientos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permiten a los usuarios insertar extensiones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bf0da-115">Behaviors in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allow users to inject extensions into the runtime.</span></span> <span data-ttu-id="bf0da-116">Este comportamiento agrega el participante de seguimiento al servicio cuando este se inicia.</span><span class="sxs-lookup"><span data-stu-id="bf0da-116">This behavior adds the tracking participant to the service when the service starts.</span></span>|  
|`TextFileTrackingParticipant`|<span data-ttu-id="bf0da-117">El participante de seguimiento que recibe los participantes de seguimiento en tiempo de ejecución y los almacena en un archivo de registro como XML.</span><span class="sxs-lookup"><span data-stu-id="bf0da-117">The tracking participant that receives tracking participants at runtime and stores them to a log file as XML.</span></span>|  
  
## <a name="behavior-extension-elements-configuration"></a><span data-ttu-id="bf0da-118">Configuración de elementos de extensión de comportamiento</span><span class="sxs-lookup"><span data-stu-id="bf0da-118">Behavior Extension Elements Configuration</span></span>  
 <span data-ttu-id="bf0da-119">Para usar mediante archivos de configuración de .NET Framework el elemento de extensión de comportamiento previamente descrito, se necesita un paso más.</span><span class="sxs-lookup"><span data-stu-id="bf0da-119">One more step is required to make use of the behavior extension element previously described using .NET Framework configuration files.</span></span> <span data-ttu-id="bf0da-120">En los archivos de configuración donde se va a usar la extensión se debe incluir la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="bf0da-120">The following configuration must be placed in configuration files where the extension is to be used.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="bf0da-121">Vea el archivo Web.config del ejemplo para el uso del ejemplo completo de la configuración de elementos de extensión de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="bf0da-121">See the Web.config file in the sample for a complete example usage of behavior extension elements configuration.</span></span>  
  
## <a name="custom-tracking-records"></a><span data-ttu-id="bf0da-122">Registros de seguimiento personalizados</span><span class="sxs-lookup"><span data-stu-id="bf0da-122">Custom Tracking Records</span></span>  
 <span data-ttu-id="bf0da-123">El archivo GetStockPrices.cs muestra cómo crear registros de seguimiento personalizados desde una actividad <xref:System.Activities.CodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="bf0da-123">The GetStockPrices.cs file demonstrates how to create custom tracking records from within a <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="bf0da-124">Busque este registro al ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bf0da-124">Look for this record when running the sample.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="bf0da-125">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf0da-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="bf0da-126">Abra el archivo de solución de WFStockPriceApplication.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf0da-126">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="bf0da-127">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="bf0da-127">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="bf0da-128">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="bf0da-128">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="bf0da-129">La ventana del explorador se abre y muestra la lista de directorios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf0da-129">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="bf0da-130">En el explorador, haga clic en StockPriceService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="bf0da-130">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="bf0da-131">El explorador muestra la **StockPriceService** página, que contiene la dirección wsdl de servicio local.</span><span class="sxs-lookup"><span data-stu-id="bf0da-131">The browser displays the **StockPriceService** page, which contains the local service wsdl address.</span></span> <span data-ttu-id="bf0da-132">Copie esta dirección.</span><span class="sxs-lookup"><span data-stu-id="bf0da-132">Copy this address.</span></span>  
  
     <span data-ttu-id="bf0da-133">Un ejemplo de dirección wsdl de servicio local es http://localhost:53797/StockPriceService.xamlx?wsdl.</span><span class="sxs-lookup"><span data-stu-id="bf0da-133">An example of the local service wsdl address is http://localhost:53797/StockPriceService.xamlx?wsdl.</span></span>  
  
6.  <span data-ttu-id="bf0da-134">Mediante [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], vaya a la carpeta de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (la carpeta de instalación predeterminada es %SystemDrive%\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="bf0da-134">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], go to your [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] folder (the default installation folder is %SystemDrive%\Program Files\Microsoft Visual Studio 10.0).</span></span> <span data-ttu-id="bf0da-135">A continuación, busque la subcarpeta Common7\IDE\.</span><span class="sxs-lookup"><span data-stu-id="bf0da-135">Then locate the Common7\IDE\ subfolder.</span></span>  
  
7.  <span data-ttu-id="bf0da-136">Haga doble clic en el archivo WcfTestClient.exe para iniciar el Cliente de prueba WCF.</span><span class="sxs-lookup"><span data-stu-id="bf0da-136">Double-click the WcfTestClient.exe file to launch the WCF Test Client.</span></span>  
  
8.  <span data-ttu-id="bf0da-137">En el cliente de prueba WCF, seleccione **Agregar servicio...**</span><span class="sxs-lookup"><span data-stu-id="bf0da-137">In the WCF Test Client, select **Add Service…**</span></span> <span data-ttu-id="bf0da-138">desde el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="bf0da-138">from the **File** menu.</span></span>  
  
9. <span data-ttu-id="bf0da-139">Pegue en el cuadro de texto la dirección URL que acaba de copiar.</span><span class="sxs-lookup"><span data-stu-id="bf0da-139">Paste the URL you just copied into the text box.</span></span>  
  
10. <span data-ttu-id="bf0da-140">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="bf0da-140">Click **OK** to close the dialog.</span></span>  
  
11. <span data-ttu-id="bf0da-141">Pruebe el servicio con el Cliente de prueba WCF.</span><span class="sxs-lookup"><span data-stu-id="bf0da-141">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="bf0da-142">En el cliente de prueba WCF, haga doble clic en **GetStockPrice()** en el **IStockPriceService** nodo.</span><span class="sxs-lookup"><span data-stu-id="bf0da-142">In the WCF Test Client, double-click **GetStockPrice()** under the **IStockPriceService** node.</span></span>  
  
         <span data-ttu-id="bf0da-143">El **GetStockPrice()** método aparece en el panel derecho, con un parámetro.</span><span class="sxs-lookup"><span data-stu-id="bf0da-143">The **GetStockPrice()** method appears in the right pane, with one parameter.</span></span>  
  
    2.  <span data-ttu-id="bf0da-144">Escriba Contoso como valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="bf0da-144">Type in Contoso as the value for the parameter.</span></span>  
  
    3.  <span data-ttu-id="bf0da-145">Haga clic en **invocar**.</span><span class="sxs-lookup"><span data-stu-id="bf0da-145">Click **Invoke**.</span></span>  
  
12. <span data-ttu-id="bf0da-146">Vea los eventos seguidos en el archivo de registro localizado en el directorio de datos de la aplicación en %APPDATA%\trackingRecords.log.</span><span class="sxs-lookup"><span data-stu-id="bf0da-146">See the tracked events in the log file located in your application data directory at %APPDATA%\trackingRecords.log.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf0da-147">% APPDATA % es una variable de entorno que se resuelve en %SystemDrive%\Users\\< nombre de usuario\>\AppData\Roaming en [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], o Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="bf0da-147">The %APPDATA% is an environment variable that resolves to %SystemDrive%\Users\\<username\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], or Windows Server 2008.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf0da-148">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bf0da-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bf0da-149">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bf0da-149">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bf0da-150">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf0da-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bf0da-151">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bf0da-151">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a><span data-ttu-id="bf0da-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf0da-152">See Also</span></span>  
 [<span data-ttu-id="bf0da-153">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="bf0da-153">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
