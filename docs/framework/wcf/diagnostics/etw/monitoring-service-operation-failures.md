---
title: Supervisar los errores de operación de servicio
ms.date: 03/30/2017
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
ms.openlocfilehash: 3d708b537789c8d0decf75df780300c1e185c4c8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="monitoring-service-operation-failures"></a><span data-ttu-id="736cc-102">Supervisar los errores de operación de servicio</span><span class="sxs-lookup"><span data-stu-id="736cc-102">Monitoring Service Operation Failures</span></span>
<span data-ttu-id="736cc-103">Si la traza analítica está habilitada para una aplicación, los errores del servicio se pueden supervisar con facilidad en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="736cc-103">If analytic tracing is enabled for an application, service failures can easily be monitored in the event viewer.</span></span>  <span data-ttu-id="736cc-104">Este tema muestra cómo determinar cuándo se produce un error en una operación del servicio y cómo determinar lo que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="736cc-104">This topic demonstrates how to determine when a service operation fails, and how to determine what caused the failure.</span></span>  
  
### <a name="determining-service-operation-failure-information"></a><span data-ttu-id="736cc-105">Determinar la información de error de la operación del servicio</span><span class="sxs-lookup"><span data-stu-id="736cc-105">Determining service operation failure information</span></span>  
  
1.  <span data-ttu-id="736cc-106">Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="736cc-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="736cc-107">Si no ha habilitado la traza analítica, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="736cc-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="736cc-108">Seleccione **vista**, **mostrar analíticos y de depuración registros**.</span><span class="sxs-lookup"><span data-stu-id="736cc-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="736cc-109">Haga clic en **analítico** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="736cc-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="736cc-110">Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se produzca el error en la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="736cc-110">Leave Event Viewer open so that traces can be viewed after the service operation fails.</span></span>  
  
3.  <span data-ttu-id="736cc-111">A continuación, abra el ejemplo creado en el [Tutorial de introducción](../../../../../docs/framework/wcf/getting-started-tutorial.md) en [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] tenga en cuenta que debe ejecutar [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] como administrador para que se puede crear el servicio.</span><span class="sxs-lookup"><span data-stu-id="736cc-111">Next, open the sample created in the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Note that you must run [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] as an administrator so that the service can be created.</span></span> <span data-ttu-id="736cc-112">Si tiene instalados los ejemplos de WCF, puede abrir el [Introducción](../../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="736cc-112">If you have the WCF samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="736cc-113">En el archivo Program.cs del proyecto Servidor, agregue la siguiente línea de código al principio del método `Divide` en la clase `CalculatorService`:</span><span class="sxs-lookup"><span data-stu-id="736cc-113">In the Program.cs file in the Server project, add the following line of code to the start of the `Divide` method in the `CalculatorService` class:</span></span>  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  <span data-ttu-id="736cc-114">En el archivo Program.cs del proyecto Cliente, cambie por cero el valor asignado a value2:</span><span class="sxs-lookup"><span data-stu-id="736cc-114">In the Program.cs file in the Client project, change the value assigned to value2 to zero:</span></span>  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  <span data-ttu-id="736cc-115">Ejecute la aplicación de servidor sin depurar presionando **CTRL+F5**.</span><span class="sxs-lookup"><span data-stu-id="736cc-115">Execute the server application without debugging by pressing **Ctrl+F5**.</span></span>  
  
7.  <span data-ttu-id="736cc-116">Abra un símbolo del sistema de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="736cc-116">Open a Visual Studio command prompt.</span></span>  <span data-ttu-id="736cc-117">Desplácese hasta el directorio de cliente y ejecute el cliente desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="736cc-117">Navigate to the client directory and execute the client from the command line.</span></span>  
  
8.  <span data-ttu-id="736cc-118">En el Visor de eventos, deshabilite el registro analítico y actualícelo, y ordene los eventos por identificador de evento.</span><span class="sxs-lookup"><span data-stu-id="736cc-118">In Event Viewer, disable and refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="736cc-119">Busque un evento con el Id. de evento [ServiceException 219 -](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), que describe el error del servicio.</span><span class="sxs-lookup"><span data-stu-id="736cc-119">Look for an event with Event ID [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), which describes the service failure.</span></span>  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="736cc-120">Los eventos se almacenan en búfer al enviarse al visor de eventos; el evento erróneo puede no aparecer enseguida.</span><span class="sxs-lookup"><span data-stu-id="736cc-120">Events are buffered when being sent to the event viewer; the failure event may not appear right away.</span></span>
