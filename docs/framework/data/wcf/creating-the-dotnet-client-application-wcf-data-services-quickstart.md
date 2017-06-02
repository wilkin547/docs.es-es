---
title: "Crear la aplicaci&#243;n cliente de .NET Framework (Tutorial r&#225;pido de WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Crear la aplicaci&#243;n cliente de .NET Framework (Tutorial r&#225;pido de WCF Data Services)
Esta es la tarea final del tutorial rápido de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  En esta tarea, agregará una aplicación de consola a la solución, agregará una referencia a la fuente de [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] en esta nueva aplicación cliente y obtendrá acceso a la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde la aplicación cliente usando las clases del servicio de datos del cliente y las bibliotecas de cliente generadas.  
  
> [!NOTE]
>  No es necesaria una aplicación cliente basada en .NET Framework para obtener acceso a una fuente de datos.  Cualquier componente de aplicación que utilice una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] puede tener acceso al servicio de datos.  Para obtener más información, consulta [Usar un servicio de datos en una aplicación cliente](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
### Para crear la aplicación cliente mediante Visual Studio  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en la solución, haga clic en **Agregar** y, a continuación, haga clic en **Nuevo proyecto**.  
  
2.  En **Tipos de proyecto**, haga clic en **Windows** y, a continuación, seleccione **Aplicación WPF** en el panel **Templates**.  
  
3.  Escriba `NorthwindClient` como nombre del proyecto y haga clic en **Aceptar**.  
  
4.  Abra el archivo MainWindow.xaml y reemplace el código XAML con el código siguiente:  
  
     [!code-xml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]  
  
### Para agregar al proyecto una referencia al servicio de datos  
  
1.  Haga clic con el botón secundario en el proyecto NorthwindClient, haga clic en **Agregar referencia de servicio** y, a continuación, haga clic en **Detectar**.  
  
     De este modo se muestra el servicio de datos de Northwind que creó en la primera tarea.  
  
2.  En el cuadro de texto **Espacio de nombres**, escriba `Northwind` y, a continuación, haga clic en **Aceptar**.  
  
     De este modo se agrega un nuevo archivo de código al proyecto, que contiene las clases de datos que se usan para obtener acceso e interactuar con los recursos del servicio de datos como objetos.  Las clases de datos se crean en el espacio de nombres `NorthwindClient.Northwind`.  
  
### Para tener acceso a los datos del servicio de datos en la aplicación WPF  
  
1.  En el **Explorador de soluciones**, en **NorthwindClient**, haga clic con el botón secundario en el proyecto y haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo Agregar referencia, haga clic en la pestaña **.NET**, seleccione el ensamblado System.Data.Services.Client.dll y, a continuación, haga clic en **Aceptar**.  En el **Explorador de soluciones**, en **NorthwindClient**, abra la página de codigos para el archivo MainWindow.xaml y agregue la instrucción `using` siguiente \(`Imports` en Visual Basic\).  
  
     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]  
  
3.  Inserte el código siguiente que consulta al servicio de datos y enlaza el resultado a una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> en la clase `MainWindow`:  
  
    > [!NOTE]
    >  Debe reemplazar el nombre de host `localhost:12345` por el servidor y el puerto en que se hospeda la instancia del servicio de datos de Northwind.  
  
     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]  
  
4.  Inserte el código siguiente que guarda los cambios en la clase `MainWindow`:  
  
     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]  
  
### Para compilar y ejecutar la aplicación NorthwindClient  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en el proyecto NorthwindClient y seleccione **Establecer como proyecto de inicio**.  
  
2.  Presione F5 para iniciar la aplicación.  
  
     Se compila la solución y se inicia la aplicación cliente.  Los datos se solicitarán al servicio y se mostrarán en la consola.  
  
3.  Edite un valor de la columna **Cantidad** de la cuadrícula de datos y, a continuación, haga clic en **Guardar**.  
  
     Los cambios se guardan en el servicio de datos.  
  
    > [!NOTE]
    >  Esta versión de la aplicación NorthwindClient no admite agregar ni eliminar entidades.  
  
## Pasos siguientes  
 Ha creado correctamente la aplicación cliente que tiene acceso a la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Northwind de ejemplo.  También ha completado el tutorial rápido de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] el acceso a una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde una aplicación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], vea [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).  
  
## Vea también  
 [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [Recursos](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)