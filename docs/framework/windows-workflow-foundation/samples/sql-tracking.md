---
title: Seguimiento de SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dcffb306c8466e63e0d5888c91d5f6015845d81c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="sql-tracking"></a><span data-ttu-id="a70b0-102">Seguimiento de SQL</span><span class="sxs-lookup"><span data-stu-id="a70b0-102">SQL Tracking</span></span>
<span data-ttu-id="a70b0-103">Este ejemplo muestra cómo escribir un participante de seguimiento SQL personalizado, que escribe registros de seguimiento en una base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="a70b0-103">This sample demonstrates how to write a custom SQL tracking participant, that writes tracking records to a SQL database.</span></span> [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="a70b0-104"> proporciona seguimiento del flujo de trabajo para ganar visibilidad en la ejecución de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a70b0-104"> provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="a70b0-105">El tiempo de ejecución de seguimiento emite registros de seguimiento de flujo de trabajo durante la ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a70b0-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a70b0-106">flujo de trabajo de seguimiento, vea [seguimiento y traza del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="a70b0-106"> workflow tracking, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a70b0-107">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a70b0-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="a70b0-108">Compruebe que tiene instalado SQL Server 2008, SQL Server 2008 Express o una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="a70b0-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="a70b0-109">Los scripts empaquetados con el ejemplo dan por supuesto el uso de una instancia de SQL Express en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="a70b0-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="a70b0-110">Si tiene una instancia diferente, modifique los scripts de base de datos antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a70b0-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>  
  
2.  <span data-ttu-id="a70b0-111">Cree la base de datos de seguimiento de SQL Server ejecutando Trackingsetup.cmd en el directorio de scripts (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span><span class="sxs-lookup"><span data-stu-id="a70b0-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="a70b0-112">De esta forma, se creará una base de datos denominada TrackingSample.</span><span class="sxs-lookup"><span data-stu-id="a70b0-112">This creates a database called TrackingSample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a70b0-113">El script crea la base de datos en la instancia predeterminada de SQL Express.</span><span class="sxs-lookup"><span data-stu-id="a70b0-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="a70b0-114">Si desea realizar la instalación en una instancia de base de datos diferente, modifique el script Trackingsetup.cmd.</span><span class="sxs-lookup"><span data-stu-id="a70b0-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>  
  
3.  <span data-ttu-id="a70b0-115">Abra SqlTrackingSample.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a70b0-115">Open SqlTrackingSample.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="a70b0-116">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="a70b0-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="a70b0-117">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a70b0-117">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="a70b0-118">La ventana del explorador se abre y muestra la lista de directorios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a70b0-118">The browser window opens and shows the directory listing for the application.</span></span>  
  
6.  <span data-ttu-id="a70b0-119">En el explorador, haga clic en StockPriceService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="a70b0-119">In the browser, click StockPriceService.xamlx.</span></span>  
  
7.  <span data-ttu-id="a70b0-120">El explorador muestra la página StockPriceService, que contiene la dirección WSDL de servicio local.</span><span class="sxs-lookup"><span data-stu-id="a70b0-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="a70b0-121">Copie esta dirección.</span><span class="sxs-lookup"><span data-stu-id="a70b0-121">Copy this address.</span></span>  
  
     <span data-ttu-id="a70b0-122">Un ejemplo de dirección WSDL de servicio local es http://localhost:65193/StockPriceService.xamlx?wsdl.</span><span class="sxs-lookup"><span data-stu-id="a70b0-122">An example of the local service WSDL address is http://localhost:65193/StockPriceService.xamlx?wsdl.</span></span>  
  
8.  <span data-ttu-id="a70b0-123">Al usar [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], ejecute el cliente de prueba de WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="a70b0-123">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="a70b0-124">Se encuentra en el directorio Microsoft Visual Studio 10.0\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="a70b0-124">It is located in the Microsoft Visual Studio 10.0\Common7\IDE directory.</span></span>  
  
9. <span data-ttu-id="a70b0-125">En el cliente de prueba WCF, haga clic en el **archivo** menú y seleccione **Agregar servicio**.</span><span class="sxs-lookup"><span data-stu-id="a70b0-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="a70b0-126">Pegue la dirección del servicio local en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="a70b0-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="a70b0-127">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a70b0-127">Click **OK** to close the dialog.</span></span>  
  
10. <span data-ttu-id="a70b0-128">En el cliente de prueba WCF, haga doble clic en **GetStockPrice**.</span><span class="sxs-lookup"><span data-stu-id="a70b0-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="a70b0-129">Se abrirá la `GetStockPrice` operación que toma un parámetro, escriba el valor `Contoso` y haga clic en **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="a70b0-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>  
  
11. <span data-ttu-id="a70b0-130">Los registros de seguimiento emitidos se escriben en una base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="a70b0-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="a70b0-131">Para ver los registros de seguimiento, abra la base de datos TrackingSample en SQL Management Studio y navegue hasta las tablas.</span><span class="sxs-lookup"><span data-stu-id="a70b0-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a70b0-132">SQL Server Management Studio, consulte [Introducción a SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).</span><span class="sxs-lookup"><span data-stu-id="a70b0-132"> SQL Server Management Studio, see [Introducing SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).</span></span> <span data-ttu-id="a70b0-133">Puede descargar SQL Server 2008 Management Studio Express [aquí](http://go.microsoft.com/fwlink/?LinkId=180520).</span><span class="sxs-lookup"><span data-stu-id="a70b0-133">SQL Server 2008 Management Studio Express can be downloaded [here](http://go.microsoft.com/fwlink/?LinkId=180520).</span></span> <span data-ttu-id="a70b0-134">La ejecución de una consulta de selección en las tablas muestra los datos dentro de los registros de seguimiento almacenados en las tablas respectivas.</span><span class="sxs-lookup"><span data-stu-id="a70b0-134">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="a70b0-135">Para desinstalar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a70b0-135">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="a70b0-136">Ejecute el script Trackingcleanup.cmd script en el directorio de ejemplo (\WF\Basic\Tracking\SqlTracking).</span><span class="sxs-lookup"><span data-stu-id="a70b0-136">Run theTrackingcleanup.cmd script in the sample directory (\WF\Basic\Tracking\SqlTracking).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a70b0-137">Trackingcleanup.cmd intenta eliminar la base de datos en el SQL Express del equipo local.</span><span class="sxs-lookup"><span data-stu-id="a70b0-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="a70b0-138">Si está utilizando otra instancia del servidor SQL, modifique Trackingcleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="a70b0-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a70b0-139">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a70b0-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a70b0-140">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a70b0-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a70b0-141">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a70b0-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a70b0-142">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a70b0-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a><span data-ttu-id="a70b0-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="a70b0-143">See Also</span></span>  
 [<span data-ttu-id="a70b0-144">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="a70b0-144">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
