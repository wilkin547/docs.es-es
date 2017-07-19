---
title: "Comportamiento de publicaci&#243;n de metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ejemplo de comportamientos de publicación de metadatos [Windows Communication Foundation]"
  - "comportamientos del servicio, ejemplo de publicación de metadatos"
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Comportamiento de publicaci&#243;n de metadatos
El ejemplo de comportamiento de publicación de metadatos muestra cómo controlar las características de publicación de metadatos de un servicio.Para evitar la divulgación involuntaria de metadatos de servicio con información confidencial potencial, la configuración predeterminada para los servicios [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] deshabilita la publicación de metadatos.Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos \(como Svcutil.exe\) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración.  
  
> [!IMPORTANT]
>  Para ser más claros, este ejemplo muestra cómo crear un extremo de publicación de metadatos no seguro.Tales extremos están disponibles de manera potencial para consumidores anónimos no autenticados y se debe tener cuidado antes de implementar tales extremos para garantizar que la revelación pública de un metadato del servicio sea adecuada.Vea el ejemplo [Extremo personalizado de metadatos seguros](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) para obtener un ejemplo en el que se proteja un extremo de metadatos.  
  
 El ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa el contrato de servicio `ICalculator`.En este ejemplo, el cliente es una aplicación de consola \(.exe\) e Internet Information Services \(IIS\) hospeda el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Para que un servicio exponga los metadatos, se debe configurar <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en el servicio.Cuando este comportamiento está presente, puede publicar los metadatos configurando un extremo para exponer el contrato <xref:System.ServiceModel.Description.IMetadataExchange> como una implementación de un protocolo WS\-MetadataExchange \(MEX\).Para su comodidad, se ha proporcionado al contrato el nombre de configuración abreviado de "IMetadataExchange."Este ejemplo utiliza `mexHttpBinding`, que es un enlace estándar de conveniencia que es equivalente a `wsHttpBinding` con el modo de seguridad establecido en `None`.Se utiliza una dirección relativa de "mex" en el extremo que, cuando se resuelve con los resultados de la dirección base de los servicios resulta en una dirección de extremo de http:\/\/localhost\/servicemodelsamples\/service.svc\/mex.A continuación, se muestra la configuración del comportamiento:  
  
```  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 A continuación, se muestra el extremo de MEX.  
  
```  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 Este ejemplo establece la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true`, que también expone los metadatos del servicio mediante HTTP GET.Para habilitar un extremo de metadatos HTTP GET, el servicio debe tener una dirección base HTTP.Se utiliza `?wsdl` de la cadena de consulta en la dirección base del servicio para tener acceso a los metadatos.Por ejemplo, para ver WSDL para el servicio en un explorador web, usaría http:\/\/localhost\/servicemodelsamples\/service.svc?wsdl.De manera alternativa, puede usar este comportamiento para exponer metadatos sobre HTTPS estableciendo <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> en `true`.Esto requiere una dirección base HTTPS.  
  
 Para tener acceso al extremo MEX del servicio, use la [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 Esto genera un cliente basado en los metadatos del servicio.  
  
 Para tener acceso a los metadatos del servicio mediante HTTP GET, introduzca en el explorador http:\/\/localhost\/servicemodelsamples\/service.svc? wsdl.  
  
 Si quita este comportamiento e intenta abrir el servicio, obtendrá una excepción.Este error se produce porque sin el comportamiento, el extremo configurado con el contrato `IMetadataExchange` no tiene ninguna implementación.  
  
 Si establece `HttpGetEnabled` en `false`, ve la página de ayuda de CalculatorService en lugar de ver los metadatos del servicio.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
  
## Vea también