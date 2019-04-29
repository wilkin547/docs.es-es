---
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 0b06d61a33cd6a704a5ab0f75d29bde3f72d77fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788432"
---
# <a name="servicemetadata"></a>\<serviceMetadata>
Especifica la publicación de metadatos e información asociada del servicio.  
  
\<system.serviceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<serviceMetadata>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceMetadata externalMetadataLocation="String"
                 httpGetBinding="String"
                 httpGetBindingConfiguration="String"
                 httpGetEnabled="Boolean"
                 httpGetUrl="String"
                 httpsGetBinding="String"
                 httpsGetBindingConfiguration="String"
                 httpsGetEnabled="Boolean"
                 httpsGetUrl="String"
                 policyVersion="Policy12/Policy15" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|externalMetadataLocation|Un URI que contiene la ubicación de un archivo WSDL que se devuelve al usuario en respuesta a las solicitudes WSDL y MEX en lugar del WSDL generado automáticamente. Cuando no se establece este atributo, se devuelve el WSDL predeterminado. El valor predeterminado es una cadena vacía.|  
|httpGetBinding|Cadena que especifica el tipo de enlace que se usará para la recuperación de metadatos a través de HTTP GET. Este valor es opcional. Si no se especifica, se usarán los enlaces predeterminados.<br /><br /> Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>. Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.|  
|httpGetBindingConfiguration|Cadena que establece el nombre del enlace que se especifica en el atributo `httpGetBinding`, que hace referencia a la información de configuración adicional de este enlace. El mismo nombre se debe definir en la sección `<bindings>`.|  
|httpGetEnabled|Un valor boolenao que especifica si publicar los metadatos del servicio para la recuperación utilizando un HTTP/Obtener solicitud. De manera predeterminada, es `false`.<br /><br /> Si no se especifica el atributo httpGetUrl, la dirección en la que se publican los metadatos es la dirección de servicio más un "? wsdl." Por ejemplo, si la dirección del servicio es "http://localhost:8080/CalculatorService", la dirección de metadatos HTTP/Get es"http://localhost:8080/CalculatorService?wsdl".<br /><br /> Si esta propiedad es `false`, o la dirección del servicio no se basa en HTTP o HTTPS, "? wsdl" se omite.|  
|httpGetUrl|URI que especifica la dirección en la que se publican los metadatos para la recuperación mediante una solicitud HTTP/Get. Si se especifica un URI relativo, se tratará como relativo a la dirección base del servicio.|  
|httpsGetBinding|Cadena que especifica el tipo de enlace que se usará para la recuperación de metadatos a través de HTTPS GET. Este valor es opcional. Si no se especifica, se usarán los enlaces predeterminados.<br /><br /> Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>. Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.|  
|httpsGetBindingConfiguration|Cadena que establece el nombre del enlace que se especifica en el atributo `httpsGetBinding`, que hace referencia a la información de configuración adicional de este enlace. El mismo nombre se debe definir en la sección `<bindings>`.|  
|httpsGetEnabled|Un valor boolenao que especifica si se van a publicar los metadatos del servicio para la recuperación mediante una solicitud HTTP/Get. De manera predeterminada, es `false`.<br /><br /> Si no se especifica el atributo httpsGetUrl, la dirección en la que se publican los metadatos es la dirección de servicio más un "? wsdl." Por ejemplo, si la dirección del servicio es "https://localhost:8080/CalculatorService", la dirección de metadatos HTTP/Get es"https://localhost:8080/CalculatorService?wsdl".<br /><br /> Si esta propiedad es `false`, o la dirección del servicio no se basa en HTTP o HTTPS, "? wsdl" se omite.|  
|httpsGetUrl|URI que especifica la dirección en la que se publican los metadatos para la recuperación mediante una solicitud HTTPS/Get.|  
|policyVersion|Una cadena que especifica la versión de la especificación WS-Policy que se va a usar. Este atributo es del tipo <xref:System.ServiceModel.Description.PolicyVersion>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración permite controlar los metadatos que publican características de un servicio. Para evitar la divulgación involuntaria de metadatos de servicio potencialmente confidenciales, la configuración predeterminada para servicios Windows Communication Foundation (WCF) deshabilita la publicación de metadatos. Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos (como Svcutil.exe) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración. Con este elemento de configuración, puede habilitar este comportamiento de publicación para su servicio.  
  
 Para obtener un ejemplo detallado de la configuración de este comportamiento, consulte [comportamiento de publicación de metadatos](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).  
  
 Los atributos `httpGetBinding` y `httpsGetBinding` opcionales le permiten configurar los enlaces utilizados para la recuperación de metadatos a través de HTTP GET (o HTTPS GET). Si no se especifican, los enlaces predeterminados (`HttpTransportBindingElement`, en el caso de HTTP y `HttpsTransportBindingElement`, en el caso de HTTPS) se utilizan según corresponda para la recuperación de metadatos. Observe que no puede utilizar estos atributos con los enlaces WCF integrados. Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>. Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
 Para reducir la exposición de un servicio a los usuarios malintencionados, es posible proteger la transferencia mediante el mecanismo SSL sobre HTTP (HTTPS). Para realizar esto, debe enlazar primero un certificado X.509 adecuado a un puerto concreto en el equipo que esté hospedando el servicio. (Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Segundo, agregue este elemento a la configuración de servicio y establezca el atributo `httpsGetEnabled` en `true`. Finalmente, establezca el atributo `httpsGetUrl` en la dirección URL del punto de conexión de metadatos del servicio, tal y como se muestra en el ejemplo siguiente.  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="NewBehavior">
      <serviceMetadata httpsGetEnabled="true"
                       httpsGetUrl="https://myComputerName/myEndpoint" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente configura un servicio para exponer los metadatos mediante el \<serviceMetadata > elemento. También configura un extremo para exponer el contrato `IMetadataExchange` como una implementación de un protocolo WS-MetadataExchange (MEX). El ejemplo usa `mexHttpBinding`, que es un enlace estándar de conveniencia equivalente a `wsHttpBinding` con el modo de seguridad establecido en `None`. Se usa una dirección relativa de "mex" en el punto de conexión, que cuando se resuelve con los servicios de bases dirección da como resultado una dirección de punto de conexión de `http://localhost/servicemodelsamples/service.svc/mex`.  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Comportamiento de publicación de metadatos](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
