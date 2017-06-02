---
title: "Activaci&#243;n basada en la configuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Activaci&#243;n basada en la configuraci&#243;n
En este ejemplo se muestra cómo activar los servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sin requerir un archivo .svc.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## Detalles del ejemplo  
 En este ejemplo, el cliente es el cliente de prueba de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y el servicio se hospeda en IIS.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
### Activación de servicios sin necesidad de un archivo .svc  
 En [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], se necesitaba un archivo .svc para activar un servicio.Esto ocasionaba sobrecarga de administración adicional, porque era necesario implementar y mantener un archivo adicional junto con la aplicación.Con la versión de [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], los componentes de activación se pueden configurar utilizando el archivo de configuración de la aplicación.  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] incluye un nuevo elemento de configuración \(<xref:System.ServiceModel.Configuration.ServiceActivationElement>\), en <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> del archivo de configuración de la aplicación.La colección de <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> acepta una colección de servicios para activar, como se muestra en el siguiente ejemplo de código.  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
  
```  
  
 Es preciso tener en cuenta una observación: la configuración parece muy similar a la configuración de archivos .svc.Se incluye un atributo adicional, `relativeAddress`, que proporciona la dirección del servicio.La dirección relativa también es la ruta de acceso virtual del servicio.El host recupera el archivo Web.config del archivo de la ubicación `virtualPath`, si está presente; de lo contrario, el host busca de forma recursiva en su carpeta primaria.  
  
> [!NOTE]
>  En este ejemplo se requiere que funcione el hospedaje en IIS.  
  
#### Para utilizar este ejemplo  
  
1.  Mediante [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo Service.csproj.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Pruebe el servicio ejecutando WCFTestClient.exe.  
  
4.  Mediante el [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navegue a la carpeta %SystemDrive%\\Archivos de programa\\Microsoft Visual Studio 10.0\\Common7\\IDE.  
  
5.  Ejecute WcfTestClient.exe.  
  
6.  Establezca la dirección MEX del servicio.  
  
7.  Presione CTRL\+MAYÚS\+A para establecer la dirección de servicio.  
  
8.  Establezca la dirección en http:\/\/localhost\/ServiceModelSamples\/Calculator.svc.  
  
9. Realice la operación `Add`.Establezca el valor del parámetro `n1` en 10 y el valor del parámetro `n2` en 15.  
  
10. Presione **Invocar**.  
  
     El resultado esperado es 25.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código de la edición .NET de C\# o Visual Basic de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Una vez compilada la solución, ejecute Setup.bat para configurar la aplicación ServiceModelSamples en IIS.El directorio ServiceModelSamples debería aparecer ahora como una aplicación IIS.  
  
4.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Vea también  
 [Ejemplos de hospedaje y persistencia de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)