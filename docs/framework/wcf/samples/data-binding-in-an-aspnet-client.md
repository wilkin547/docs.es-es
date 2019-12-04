---
title: Enlace de datos en un cliente ASP.NET
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: 2db29e0c4cdb87961430b80f317160b90e6756d0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715377"
---
# <a name="data-binding-in-an-aspnet-client"></a>Enlace de datos en un cliente ASP.NET
Este ejemplo muestra cómo enlazar los datos devueltos por un servicio de Windows Communication Foundation (WCF) típico en una aplicación de formularios Web Forms.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo muestra un servicio que implementa un contrato que define un patrón de comunicación de solicitud y respuesta. El ejemplo consta de una aplicación de formularios Web Forms de cliente accesible desde un explorador y un servicio WCF hospedado por Internet Information Services (IIS).  
  
 El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta. El contrato se define mediante la interfaz `IWeatherService`, que expone una operación denominada `GetWeatherData`. Esta operación acepta una matriz de ciudades y devuelve una matriz de objetos `WeatherData` que representan la temperatura alta y baja prevista para una ciudad.  
  
 En la página ASP.NET Client. aspx, se define un control Web DataGrid que contiene la representación gráfica de los datos devueltos por el servicio. El código de la página. aspx llama al servicio WCF para los datos meteorológicos y devuelve los datos a una matriz de objetos `WeatherData`. DataGrid especifica de dónde obtener sus datos estableciendo su propiedad `DataSource` en esa matriz. El enlace de datos se produce con una llamada al método `DataBind` de DataGrid. Todo este código se encuentra dentro de.`aspx` `Page_Load` método de la página, por lo que cada vez que el usuario actualiza la página del explorador, los datos se actualizan en el control DataGrid.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. El cliente de este ejemplo es un sitio web que se ejecuta bajo un servidor web de desarrollo. Para iniciar el servidor Web de desarrollo, escriba lo siguiente en el símbolo del sistema: `%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`. A continuación, vaya a `http://localhost:8000/client`. Para ejecutar este ejemplo en los equipos, reemplace todas las referencias a `localhost` en el archivo Web.config del cliente con el nombre de equipo del servidor.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`
