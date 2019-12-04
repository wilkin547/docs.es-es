---
title: Comportamiento de publicación de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
ms.openlocfilehash: 3b3057d845ac37280ff46e6e15415758f1f0ba77
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714790"
---
# <a name="metadata-publishing-behavior"></a>Comportamiento de publicación de metadatos
El ejemplo de comportamiento de publicación de metadatos muestra cómo controlar las características de publicación de metadatos de un servicio. Para evitar la revelación involuntaria de metadatos de servicio potencialmente confidenciales, la configuración predeterminada de los servicios Windows Communication Foundation (WCF) deshabilita la publicación de metadatos. Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos (como Svcutil.exe) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración.  
  
> [!IMPORTANT]
> Para mostrar más claridad, este ejemplo muestra cómo crear un punto de conexión de publicación de metadatos no se seguros. Tales extremos pueden estar disponibles para los consumidores anónimos no autenticados y se debe tener cuidado antes de implementar tales extremos para garantizar que la revelación pública de un metadato del servicio sea la adecuada. Vea el ejemplo de [extremo de metadatos seguro personalizado](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) para obtener un ejemplo que protege un punto de conexión de metadatos.  
  
 El ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa el contrato de servicio `ICalculator`. En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Para que un servicio exponga los metadatos, se debe configurar <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en el servicio. Cuando este comportamiento está presente, puede publicar los metadatos configurando un extremo para exponer el contrato <xref:System.ServiceModel.Description.IMetadataExchange> como una implementación de un protocolo WS-MetadataExchange (MEX). Para su comodidad, se ha proporcionado al contrato el nombre de configuración abreviado de "IMetadataExchange." Este ejemplo utiliza `mexHttpBinding`, que es un enlace estándar de conveniencia que es equivalente a `wsHttpBinding` con el modo de seguridad establecido en `None`. Se utiliza una dirección relativa de "Mex" en el punto de conexión, que cuando se resuelve con la dirección base de los servicios, da como resultado una dirección de extremo de `http://localhost/servicemodelsamples/service.svc/mex`. A continuación, se muestra la configuración del comportamiento:  
  
```xml  
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
  
 A continuación, se muestra el punto de conexión de MEX.  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 Este ejemplo establece la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true`, que también expone los metadatos del servicio mediante HTTP GET. Para habilitar un punto de conexión de metadatos HTTP GET, el servicio debe tener una dirección base HTTP. Se utiliza `?wsdl` de la cadena de consulta en la dirección base del servicio para tener acceso a los metadatos. Por ejemplo, para ver el WSDL del servicio en un explorador Web, usaría la dirección `http://localhost/servicemodelsamples/service.svc?wsdl`. De manera alternativa, puede usar este comportamiento para exponer metadatos sobre HTTPS estableciendo <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> en `true`. Esto requiere una dirección base HTTPS.  
  
 Para tener acceso al punto de conexión MEX del servicio, use la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 Esto genera un cliente basado en los metadatos del servicio.  
  
 Para tener acceso a los metadatos del servicio mediante HTTP GET, apunte el explorador a `http://localhost/servicemodelsamples/service.svc?wsdl`.  
  
 Si quita este comportamiento e intenta abrir el servicio, obtendrá una excepción. Este error se produce porque sin el comportamiento, el extremo configurado con el contrato `IMetadataExchange` no tiene ninguna implementación.  
  
 Si establece `HttpGetEnabled` en `false`, ve la página de ayuda de CalculatorService en lugar de ver los metadatos del servicio.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
