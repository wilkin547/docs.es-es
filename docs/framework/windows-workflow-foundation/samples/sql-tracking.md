---
title: "Seguimiento de SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Seguimiento de SQL
Este ejemplo muestra cómo escribir un participante de seguimiento SQL personalizado, que escribe registros de seguimiento en una base de datos SQL.[!INCLUDE[wf](../../../../includes/wf-md.md)] proporciona seguimiento de flujo de trabajo para ganar visibilidad en la ejecución de una instancia de flujo de trabajo.El tiempo de ejecución de seguimiento emite registros de seguimiento de flujo de trabajo durante la ejecución del flujo de trabajo.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] el seguimiento del flujo de trabajo, vea [Seguimiento y traza del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  
  
#### Para utilizar este ejemplo  
  
1.  Compruebe que tiene instalado SQL Server 2008, SQL Server 2008 Express o una versión más reciente.Los scripts empaquetados con el ejemplo dan por supuesto el uso de una instancia de SQL Express en su equipo local.Si tiene una instancia diferente, modifique los scripts de base de datos antes de ejecutar el ejemplo.  
  
2.  Cree la base de datos de seguimiento de SQL Server ejecutando Trackingsetup.cmd en el directorio de scripts \(\\WF\\Basic\\Tracking\\SqlTracking\\CS\\Scripts\).De esta forma, se creará una base de datos denominada TrackingSample.  
  
    > [!NOTE]
    >  El script crea la base de datos en la instancia predeterminada de SQL Express.Si desea realizar la instalación en una instancia de base de datos diferente, modifique el script Trackingsetup.cmd.  
  
3.  Abra SqlTrackingSample.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
4.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
5.  Presione F5 para ejecutar la aplicación.  
  
     La ventana del explorador se abre y muestra la lista de directorios de la aplicación.  
  
6.  En el explorador, haga clic en StockPriceService.xamlx.  
  
7.  El explorador muestra la página StockPriceService, que contiene la dirección WSDL de servicio local.Copie esta dirección.  
  
     Un ejemplo de dirección WSDL de servicio local es http:\/\/localhost:65193\/StockPriceService.xamlx?wsdl.  
  
8.  Con el [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], ejecute el cliente de prueba WCF \(WcfTestClient.exe\).Se encuentra en el directorio Microsoft Visual Studio 10.0\\Common7\\IDE.  
  
9. En el cliente de pruebas de WCF, haga clic en el menú **Archivo** y seleccione **Agregar servicio**.Pegue la dirección del servicio local en el cuadro de texto.Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
10. En el cliente de prueba de WCF, haga doble clic en **GetStockPrice**.Se abrirá la operación `GetStockPrice` que toma un parámetro, escriba el valor `Contoso` y haga clic en **Invocar**.  
  
11. Los registros de seguimiento emitidos se escriben en una base de datos SQL.Para ver los registros de seguimiento, abra la base de datos TrackingSample en SQL Management Studio y navegue hasta las tablas.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] SQL Server Management Studio, vea [Introducción a SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).SQL Server 2008 Management Studio Express se puede descargar [aquí](http://go.microsoft.com/fwlink/?LinkId=180520).La ejecución de una consulta de selección en las tablas muestra los datos dentro de los registros de seguimiento almacenados en las tablas respectivas.  
  
#### Para desinstalar el ejemplo  
  
1.  Ejecute el script Trackingcleanup.cmd script en el directorio de ejemplo \(\\WF\\Basic\\Tracking\\SqlTracking\).  
  
    > [!NOTE]
    >  Trackingcleanup.cmd intenta eliminar la base de datos en el SQL Express del equipo local.Si está utilizando otra instancia del servidor SQL, modifique Trackingcleanup.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)