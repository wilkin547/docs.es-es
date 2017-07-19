---
title: "Enlace de datos en un cliente ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Enlace de datos en un cliente ASP.NET
Este ejemplo muestra cómo enlazar los datos devueltos por un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] típico en una aplicación formularios Web Forms.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo muestra un servicio que implementa un contrato que define un modelo de comunicación de solicitud y respuesta.El ejemplo está compuesto de una aplicación de formularios Web Forms de un cliente accesible desde un explorador y un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedado por Internet Information Services \(IIS\).  
  
 El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.El contrato se define mediante la interfaz `IWeatherService`, que expone una operación denominada `GetWeatherData`.Esta operación acepta una matriz de ciudades y devuelve una matriz de objetos `WeatherData` que representan la temperatura alta y baja prevista para una ciudad.  
  
 En la página .aspx del cliente [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], se define un control web DataGrid que contiene la representación gráfica de los datos devueltos por el servicio.El código en la página .aspx llama al servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para los datos del tiempo y devuelve los datos a una matriz de los objetos `WeatherData`.DataGrid especifica de dónde obtener sus datos estableciendo su propiedad `DataSource` en esa matriz.El enlace de datos se produce con una llamada al método `DataBind` de DataGrid.Todo este código se contiene dentro del método `Page_Load` de la página `aspx`, por lo que cada vez que el usuario actualiza la página de explorador, los datos se actualizan en DataGrid.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  El cliente de este ejemplo es un sitio web que se ejecuta bajo un servidor web de desarrollo.Para iniciar el servidor web de desarrollo, escriba lo siguiente en el símbolo del sistema: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`.A continuación, vaya a http:\/\/localhost:8000\/client.Para ejecutar este ejemplo en los equipos, reemplace todas las referencias a `localhost` en el archivo Web.config del cliente con el nombre de equipo del servidor.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## Vea también